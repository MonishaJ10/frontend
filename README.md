Inventory-configuration-->inventory-sidebar-->manage-dashboard-->blank-dashboard
blank-dashboard.component.html
<div *ngIf="showModal" class="modal-container" [class.fullscreen]="isFullscreen">
<div class="modal-box">
<div class="modal-header">
<div class="header-left">
<span class="material-symbols-outlined icon">Dashboard</span>

<h2>{{ formData.name || 'New Dashboard' }}</h2>

</div>

<div class="header-actions">

<button (click)="toggleFullscreen()" title="Fullscreen"></button>

<button (click)="closeModal()" title="Close">X</button>

</div>

</div>

<div class="step-tracker">

<div *ngFor-"let step of steps; let i index" class="step-item" [class.active]-"1 -currentStep">

<div class="step-circle">{{1+1)}</div>

<span class="step-label">{{ step }}</span>

</div>

</div>

<div class="modal-content">

<!-- Step 1: Initial ->

<form *ngIf-"currentStep 0" #dashboardForm-"ngForm" class="form-section">

<div class="form-group">

<label>Name <span class="required">*</span></label>

<input type="text" [(ngModel)]="formData.name" name="name" placeholder="Add a name" required /> </div>

<div class="form-group">

<label>Description</label>

<textarea [(ngModel)]-"formData.description" name="description" placeholder-"Mention description..."></textarea>

</div>
<div class="form-group">
<label>Description</label>

< </div>

textarea [(ngModel)]="formData.description" name="description" placeholder="Mention description..."></textarea>

<div class="form-group">

<label>Mark Dashboard As <span class="required">*</span></label>

<div class="radio-options">

<label>

<input type="radio" [(ngModel)]="formData.visibility" name="visibility" value="Public" />

<span class="custom-radio"></span> Public

</label>

<label>

<input type="radio" [(ngModel)]="formData.visibility" name="visibility" value="Private" />

<span class="custom-radio"></span> Private

</label>

</div>

<small>Select <strong>Private</strong> to assign this dashboard to one or more users or teams.</small>

</div>

</form>

<!-- Step 2: Content ->

<div *ngIf="currentStep ===1" class="content-step" style="display: flex;">

<div class="sidebar" style="flex: 1; padding: 1rem;">

<h4>Select Card</h4>

<ul>

<li [ class.active]="selectedChart 'bar'" (click)="setChartType('bar')">Case Queue by Data Element (Bar Chart)</li>

<li </ul>

[class.active]="selectedChart 'pie'" (click)="setChartType('pie')">Case Queue by Data Element (Pie Chart)</li>

</div>

<div class="chart-preview" style="flex: 2; padding: 1rem;">

<ng-container [ngSwitch]-"selectedChart">
<div class="form-group">

<label>Description</label>

< </div>

textarea [(ngModel)]="formData.description" name="description" placeholder="Mention description..."></textarea>

<div class="form-group">

<label>Mark Dashboard As <span class="required">*</span></label>

<div class="radio-options">

<label>

<input type="radio" [(ngModel)]="formData.visibility" name="visibility" value="Public" />

<span class="custom-radio"></span> Public

</label>

<label>

<input type="radio" [(ngModel)]="formData.visibility" name="visibility" value="Private" />

<span class="custom-radio"></span> Private

</label>

</div>

<small>Select <strong>Private</strong> to assign this dashboard to one or more users or teams.</small>

</div>

</form>

<!-- Step 2: Content ->

<div *ngIf="currentStep ===1" class="content-step" style="display: flex;">

<div class="sidebar" style="flex: 1; padding: 1rem;">

<h4>Select Card</h4>

<ul>

<li [ class.active]="selectedChart 'bar'" (click)="setChartType('bar')">Case Queue by Data Element (Bar Chart)</li>

<li </ul>

[class.active]="selectedChart 'pie'" (click)="setChartType('pie')">Case Queue by Data Element (Pie Chart)</li>

</div>

<div class="chart-preview" style="flex: 2; padding: 1rem;">

<ng-container [ngSwitch]-"selectedChart">
[01-06-2025 19:30] Moni: <select (ngModel)]="groupBy" name="groupBy" required>

<option *ngFor="let group of groupByOptions" [value]="group">{{ group )}</option>

</select>

<label>Aggregation</label>

<select [(ngModel)]="aggregation" name="aggregation">

<option *ngFor-"let agg of aggregationTypes" [value]="agg">{{agg}}</option>

</select>

<label>Aggregation Field</label>

<select [(ngModel)]="aggregationField" name="aggregationField">

<option *ngFor-"let field of aggregationFields" [value]="field">{{ field }}</option>

</select>

<button class="btn add-btn" style="margin-top: 10px;" (click)="addCard ()">Add</button>

</div>

</div>

</div>

<!-- Step 3: Layout -->

<div *ngIf="currentStep2" class="content-step">

<div class="chart-preview">

<ng-container (ngSwitch]="selectedChart">

<div *ngSwitchCase="'bar'">

<h3>Bar Chart Preview</h3>

<div class="chart-bar chart-container">

<ag-charts [options]="barChartOptions"></ag-charts>

</div>

</div>

<div *ngSwitchCase="'pie'">

<h3>Pie Chart Preview</h3>

<div class="chart-pie chart-container">

<ag-charts [options]-"pieChartOptions"></ag-charts>

</div>
</div>
</ng-containers>
</div>
</div>

<!-- Step 4: Review -->

<div *ngIf="currentStep === 3">

<h4>Review & Confirm</h4>

<div class="review-section">

<h5>Step 1: General Info</h5>

<p><strong>Name:</strong> {{ formData.name }}</p>

<p><strong>Description:</strong> (( formData.description || 'N/A' }}</p>

<p><strong>Visibility:</strong> {{ formData.visibility }}</p>

<h5>Step 2: Chart Configuration</h5>

<p><strong>Chart Type:</strong> {{ selectedChart == 'bar'? 'Bar Chart': 'Pie Chart' }}</p>

<p><strong>Title:</strong> {{ title }}</p>

<p><strong>Model:</strong> {{ model }}</p>

<p><strong>Group By:</strong> (( groupBy }}</p>

<p><strong>Aggregation Type:</strong> {{ aggregation }}</p>

<p><strong>Aggregation Field:</strong> {{ aggregationField)}</p>

</div>

<div class="nav-buttons">

<button class="btn primary" (click)="submit()">Finish</button>

</div>

</div>

</div>

<div class="nav-buttons">

<button class="btn secondary" (click)-"prevStep()" *ngIf="currentStep > 0">Back</button>

<button class="btn primary" (click)-"nextStep()" *ngIf="currentStep < 3">Next</button>

</div>
<</div>
</div>


blank-dashboard.component.ts

import (getData) from './////data';
import { Component, Input) from '@angular/core';
import (FormsModule} from '@angular/forms';
import { CommonModule } from '@angular/common';
import { Router } from '@angular/router';
import { AgChartsModule) from "ag-charts-angular";
import ( AgChartOptions) from 'ag-charts-community';
import (DashboardService } from '../dashboard.service';
@Component({

selector: 'app-blank-dashboard',

imports: [FormsModule, CommonModule, AgChartsModule),

templateUrl: './blank-dashboard.component.html',

styleUrls: ['./blank-dashboard.component.css']

})

export class BlankDashboardComponent (

barChartUrl: string;

pieChartUrl: string;

showModal true;

isFullscreen = false;

currentStep = 0;

steps ['Initial', 'Content', 'Layout', 'Review'];

formData

name:"

description: '',

visibility: 'Public'
selectedChart 'bar';

title

model = '';

groupBy';

aggregation = '';

aggregationField = '';

modelOptions = ['Germany_Holdings', 'Luxembourg_Holdings', 'Monacco_Holdings'];

groupByOptions ['Amount', 'Case Id', 'Create Date', 'Custom Value'];

aggregationTypes ['Count', 'Sum', 'Average', 'Max', 'Min'];

aggregationFields ['Total Amount', 'Case Number', 'Score'];

dashboardClose: any;

barChartOptions: AgChartOptions {

data: getData(),

series: this.modelOptions.map(model => ({

type: "bar" as const,

xKey: "quarter",

yKey: model,

yName: model,

1:

pieChartOptions: AgChartOptions

data: getData(),

title: {

text: "Portfolio Composition",

1.

series: {

type: "pie",

angleKey: "Amount",

calloutLabelKey: "quarter",
sectorLabelKey: "Amount",

sectorLabel: (

color: "white",

fontWeight: "bold",

formatter: ({ value }) => $${(value / 1000).toFixed (0))K',

۱۰

constructor (private router: Router, private dashboardService: DashboardService) [

this.barChartUrl 'https://isuite-evaluation.dev.echonet/ISUITE/NextGen/assets/barchart.png';

this.pieChartUrl = 'https://isuite-evaluation.dev.echonet/ISUITE/NextGen/assets/piechart.png';

toggleFullscreen() (

this.isFullscreen !this.isFullscreen;

closeModal() (

this.showModal false;

if (this.dashboardClose) (

this.dashboardClose.emit();

nextStep() {

if (this.currentStep 0 && !this.formData.name.trim()) { alert('Please fill in the required "Name" field.");


return;

}
nextStep() {

if (this.currentStep=0&& !this.formData.name.trim()) { alert('Please fill in the required "Name" field.');

return;

}

if (this.currentStep < this.steps.length-1) {

this.currentStep++;

}

prevStep() {

if (this.currentStep > 0) {

this.currentStep--;

submit() (

const dashboard =

name: this.formData.name,

description: this.formData.description,

createdBy: 'admin',

createdDate: new Date().toISOString(),

modifiedBy: 'admin',

modifiedDate: new Date().toISOString(),

isPublic: this.formData.visibility = 'Public',

model: this.model,

groupBy: this.groupBy,

aggregation: this.aggregation,

aggregationField: this.aggregationField};
this.dashboardService.addDashboard (dashboard).subscribe((

next: () => {

alert('Dashboard saved successfully!');

this.router.navigate(['/inventory/manage-dashboard']);

1,

error: (err) => {

console.error('Failed to save dashboard:',err);

alert('Failed to save dashboard');

}

});

setChartType (type: string): void {

this.selectedChart type;

this.title 'Case Queue by Data Element of type $(type = 'bar'? 'Bar Chart': 'Pie Chart')';

}

addCard(): void (

// Validation logic and storing form values

console.log('Card added:', {

chartType: this.selectedChart,

title: this.title,

model: this.model,

groupBy: this.groupBy,

aggregationField: this.aggregationField

);
}



dashboard.model.ts
export interface Dashboardd(
id: number;
name: String;
description: string;
public: boolean;
createdBy: string;
createdDate: string;
modifiedBy?: string;
modifiedDate?: string;
[key: string]: any;
}


dashboard.service.ts
import (Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import (Dashboardd } from './dashboard.model';
import { Observable } from 'rxjs';
@Injectable({
providedIn: 'root'
})

export class DashboardService {

private apiUrl = 'http://localhost:8083/api/dashboards';

constructor (private http: HttpClient) {}

get Dashboards(): Observable<Dashboardd []>{

console.log('Calling API:', this.apiUrl);

return this.http.get<Dashboardd[]> (this.apiUrl);

} addDashboard (dashboard: any): Observable<any>{ return this.http.post(this.apiUrl, dashboard);



manage-dashboard.html
<div class="manage-dashboard-container">
<!-- Main Manage Dashboard View -->
<div *ngIf="!showBlankDashboard && ! showInteractiveDashboard">
<!-- Header -->
<div class="header">
<h2 class="title">Manage Dashboard</h2>
<button class="close-btn" (click)="onClose()">×</button>
</div>
<!-- New Dashboard Button -->>

<div class="new-dashboard-section">

<button class="new-dashboard-btn" (click)="onNewDashboard ()">

<span class="plus-icon">+</span>

New Dashboard

</button>

</div>

<!-- Dashboard Types -->

<div class="dashboard-types">

<div

class="dashboard-card"

*ngFor="let dashboard of dashboards"

(click)="onSelect Dashboard (dashboard.id)"

<div class="dashboard-icon">{{dashboard.icon)}</div>

<div class="dashboard-name">{{dashboard.name})</div>

</div>

</div>

<!-- All Dashboards Section -->

<div class="all-dashboards-section">

<h3 class="section-title">All Dashboards</h3>
<!-- Table -->

<div class="table-container">

<table class="dashboards-table">

<thead>

<tr>

<th *ngFor="let header of tableHeaders">[(header.label})</th>

</tr>

</thead>

<tr *ngIf="tableData.length 0" class="no-data-row">

<tbody>

<td [attr.colspan]="tableHeaders.length" class="no-data-cell">

No Rows To Show

</td>

</tr>

<!-- Future data rows will be rendered here -->

<tr *ngFor-"let row of tableData">

<td *ngFor="let header of tableHeaders">

<!-- {{row[header.toLowerCase().replace('', '')])) -->

<ng-container [ngSwitch]="header.key">

<span *ngSwitchCase="'createdDate'">{{row.createdDate | date: 'short']}</span>

<span *ngSwitchCase="'modifiedDate'">{{row.modifiedDate | date: 'short']}</span>

<span *ngSwitchCase-"'public'">((row.public ? 'Yes': 'No')]</span>

<span *ngSwitchDefault>((row [header.key])}</span>

</ng-container>

</td>

</tr>

</tbody>

</table>

</div>

</div>

</div>
- Blank Dashboard View -->

<div "ngif "showBlankDashboard">

<app-blank-dashboard> </app-blank-dashboard>

</div>

<<1-- Interactive Dashboard View->

<div *nglf-"showInteractiveDashboard" class="dashboard-view">

<div class="dashboard-header">

<button class="back-btn" (click)-"onBackToManage ()">- Back to Manage</button>

<button class="close-btn" (click)-"onClose ()">x</button>

</div>

<- Add your interactive dashboard component here -->

<-<app-interactive-dashboard> </app-interactive-dashboard> -->

<div class="placeholder">Interactive Dashboard Component will be rendered here</div>
</div>
</div>



manage-dashboard.ts
import (Component, Event Emitter, Output from '@angular/core';
import (DashboardService) from './dashboard.service';
Import (NgIf from '@angular/common';
Import { CommonModule from '@angular/common';
import OnInit) from '@angular/core':
import (InteractiveDashboardComponent) from './interactive-dashboard/interactive-dashboard.component';

import (BlankDashboardComponent } from './blank-dashboard/blank-dashboard.component';

import Dashboardd) from './dashboard.model';

@Component({

selector: 'app-manage-dashboard',

imports: (Blank DashboardComponent, InteractiveDashboardComponent, NgIf, CommonModule], templateUrl: './manage-dashboard.component.html",

styleUrl: './manage-dashboard.component.css'

export class ManageDashboardComponent (

tableData: Dashboardd[]-[]:

dashboards[

id: 'blank',

name: 'Blank Dashboard'.

icon:

description: 'Start with a blank canvas'

id: 'interactive',

name: 'Interactive Dashboard',

icon:

description: 'Pre-built interactive components'
}];
tableHeaders=[

{key: 'name', label: 'Name'),

{key: 'description', label: 'Description'},

(key: 'createdBy', label: 'Created By'),

{key: 'createdDate', label: 'Created Date'),

{key: 'modifiedBy', label: 'Modified By'),

(key: 'modifiedDate', label: 'Modified Date'},

(key: 'public', label: 'Public'),

{key: 'action', label: 'Action'),

1:

// closeDashboard: any;

constructor (private dashboardService: DashboardService) ()

@Output() closeDashboard = new Event Emitter<void>();

@Output() selectDashboard new Event Emitter<string>();

showBlankDashboard = false;

showInteractiveDashboard false;

ngonInit():void {

this.loadDashboards();

J

loadDashboards() {

this.dashboardService.getDashboards().subscribe ({ next: (data) => this.tableData data, error: () => alert('Failed to load dashboards') });

onClose():void (

this.closeDashboard.emit();
}
onSelect Dashboard (dashboardType: string):void {

if (dashboardType == 'blank') (

this.showBlankDashboard=true;

this.showInteractiveDashboard=false;

}

else if (dashboardType'interactive') {

this.showInteractiveDashboard=true;

this.showBlankDashboard=false;

this.selectDashboard.emit (dashboardType);

onBackToManage () {

this.showBlankDashboard=false;

this.showInteractiveDashboard=false;

}

onNewDashboard() {

// Handle new dashboard creation

console.log('New Dashboard clicked');
}}

.
app.component.html
<app-header
[openedModule]="openedModule"
(toggle)-"handleToggle()"
(closeModule)-"closeModule()"
></app-header>
<div class="layout">
<ng-container *ngIf="sidebarVisible">
<!-- Show main sidebar only if no module is opened -->
<app-sidebar
*ngIf-"!openedModule"

(moduleSelected)-"openModule ($event)"

></app-sidebar>

<!-- Show inventory sidebar -->

<app-inventory-sidebar

*ngIf="openedModule 'Inventory Configuration'"

(navigate)-"navigateToSubModule (Sevent)"

></app-inventory-sidebar>

<!-- Add other sidebars for other modules here if needed -->

</ng-container>

<div class="content">

<!-- Submodule components shown based on selectedSubModule -->

<ng-container *ngIf="openedModule 'Inventory Configuration">

<div *ngIf="selectedSubModule 'manage-dashboard"">

<app-manage-dashboard></app-manage-dashboard>

<button (click)-"closeSubModule ()">Close</button>

</div>

<div ngIf="selectedSubModule 'recon-view-manager'"> <app-recon-view-manager></app-recon-view-manager>

<button (click)-"closeSubModule()">Close</button>

</div>
<div *ngIf="selectedSubModule === 'model-categories'">

<app-model-categories></app-model-categories>

<button (click)="closeSubModule()">Close</button>

</div>

</ng-container>

<!-- Default router outlet if no submodule is selected -->

<router-outlet *ngIf="! selectedSubModule"></router-outlet>

</div>

/div>

 
 
 
 app.component.ts
import | Component } from '@angular/core';
import ( RouterModule, Router) from '@angular/router';
import (CommonModule) from '@angular/common';
import | HeaderComponent } from './header/header.component';
import { SidebarComponent } from './sidebar/sidebar.component'; import { InventorySidebarComponent } from
'./pages/inventory-configuration/inventory-sidebar/inventory-sidebar.component'; import { ManageDashboardComponent } from './pages/inventory-configuration/inventory-sidebar/manage-dashboard/manage-dashboard.component import (ReconViewManagerComponent } from '

./pages/inventory-configuration/inventory-sidebar/recon-view-manager/recon-view-manager.compr import (ModelCategoriesComponent } from './pages/inventory-configuration/inventory-sidebar/model-categories/model-categories.component

@Component({

selector: 'app-root',

standalone: true,

imports: [

CommonModule,

RouterModule,

HeaderComponent,

SidebarComponent,

Inventory SidebarComponent,

ManageDashboardComponent,

ReconViewManagerComponent,

ModelCategoriesComponent,

1.

templateUrl: './app.component.html",

styleurls: ['./app.component.css'],

export class AppComponent (

sidebarVisible false;

openedModule: string | null null;

selectedSubModule: string null null;

// E.g. 'Inventory Configuration'

// E.g. 'manage-dashboard'

constructor(private router: Router) ()

// Toggle sidebar visibility

handleToggle() {

this.sidebarVisible!this.sidebarVisible;

if (!this.sidebarVisible) {

this.openedModule null;

this.selectedSubModule = null;

this.router.navigate(['']); // Default/blank route

1

// Open main module

openModule (moduleName: string) {

this.openedModule moduleName;

this.selectedSubModule null;

this.sidebarVisible true;

if (moduleName = 'Inventory Configuration') {

this.router.navigate(['/inventory-dashboard']); // Optional: default submodule

}

// Close main module

closeModule() {

this.openedModule null;

this.selectedSubModule = null;

this.router.navigate(['']);

// Open submodule within main module

navigateToSubModule (subRoute: string) {

this.selectedSubModule subRoute:

this.router.navigate([^/inventory/${subRoute)'));

/ Close only submodule

closeSubModule() {

this.selectedSubModule = null;

this.router.navigate(['/inventory-dashboard'));

}

// selectedSubModule: string | null = null;

// navigateToSubModule (name: string) {

//this.selectedSubModule = name;

// }

setSelectedSubModule (name: string) {

this.selectedSubModule = name;
}}




app.routes.ts
import (Routes) from '@angular/router';
import | InventoryConfigurationComponent } from './pages/inventory-configuration/inventory-configuration.component';
import (SystemSetupComponent } from './pages/system-setup/system-setup.component';
import (AdminComponent from './pages/admin/admin.component';
import | Import ExportManagerComponent } from './pages/import-export-manager/import-export-manager.component';
import { BlankComponent from './pages/blank/blank.component';
import | ManageDashboardComponent) from './pages/inventory-configuration/inventory-sidebar/manage-dashboard/manage-dashboard.component
import ReconViewManagerComponent) from './pages/inventory-configuration/inventory-sidebar/recon-view-manager/recon-view-manager.compo import { ModelCategoriesComponent } from './pages/inventory-configuration/inventory-sidebar/model-categories/model-categories.component
export const routes: Routes = [

(path:", component: BlankComponent ),

(path: 'inventory',

component: InventoryConfigurationComponent,

children: [

{ path: 'manage-dashboard', component: ManageDashboardComponent 1. (path: 'recon-view-manager', component: ReconViewManagerComponent },

path: 'model-categories', component: ModelCategoriesComponent ),

I path: '', redirectTo: 'manage-dashboard', pathMatch: 'full'}

1

path: 'system-setup', component: SystemSetupComponent),

(path: 'admin', component: AdminComponent 1.
( path: 'import-export', component: ImportExportManagerComponent }

app.config.tsimport | ApplicationConfig, provideZoneChangeDetection from '@angular/core';

import provideRouter) from '@angular/router':

import routes | from './app.routes';

import | bootstrapApplication, provideClientHydration, with Event Replay) from '@angular/platform-browser';

import | provideHttpClient) from '@angular/common/http';

import AppComponent } from './app.component';

export const appConfig: ApplicationConfig = {

providers: [provideHttpClient(),provideZoneChangeDetection({ eventCoalescing: true }), provideRouter (routes), provideClientHydration (


____________________________________
Thanks for the clarification! Since you're using standalone components (no AppModule), we’ll import Angular Material modules directly in the component where they're needed.

Here’s a complete update to support edit (pen icon) and delete (trash icon) functionality using Angular Material UI:


---

✅ 1. Update manage-dashboard.component.ts

Add the HTTP calls for delete and edit. We’ll simulate an “edit” by passing data to the blank dashboard component.

import { Component, EventEmitter, Output, OnInit } from '@angular/core';
import { CommonModule } from '@angular/common';
import { NgIf } from '@angular/common';
import { MatIconModule } from '@angular/material/icon';
import { MatButtonModule } from '@angular/material/button';
import { DashboardService } from './dashboard.service';
import { Dashboardd } from './dashboard.model';
import { BlankDashboardComponent } from './blank-dashboard/blank-dashboard.component';
import { InteractiveDashboardComponent } from './interactive-dashboard/interactive-dashboard.component';

@Component({
  selector: 'app-manage-dashboard',
  standalone: true,
  imports: [
    CommonModule,
    NgIf,
    MatIconModule,
    MatButtonModule,
    BlankDashboardComponent,
    InteractiveDashboardComponent
  ],
  templateUrl: './manage-dashboard.component.html',
  styleUrls: ['./manage-dashboard.component.css']
})
export class ManageDashboardComponent implements OnInit {
  tableData: Dashboardd[] = [];
  selectedDashboard: Dashboardd | null = null;
  showBlankDashboard = false;
  showInteractiveDashboard = false;

  @Output() closeDashboard = new EventEmitter<void>();
  @Output() selectDashboard = new EventEmitter<string>();

  constructor(private dashboardService: DashboardService) {}

  ngOnInit(): void {
    this.loadDashboards();
  }

  loadDashboards() {
    this.dashboardService.getDashboards().subscribe({
      next: (data) => (this.tableData = data),
      error: () => alert('Failed to load dashboards'),
    });
  }

  onClose(): void {
    this.closeDashboard.emit();
  }

  onSelectDashboard(dashboardType: string): void {
    if (dashboardType === 'blank') {
      this.showBlankDashboard = true;
      this.showInteractiveDashboard = false;
    } else if (dashboardType === 'interactive') {
      this.showInteractiveDashboard = true;
      this.showBlankDashboard = false;
      this.selectDashboard.emit(dashboardType);
    }
  }

  onEditDashboard(dashboard: Dashboardd): void {
    this.selectedDashboard = dashboard;
    this.showBlankDashboard = true;
    this.showInteractiveDashboard = false;
  }

  onDeleteDashboard(id: number): void {
    if (confirm('Are you sure you want to delete this dashboard?')) {
      this.dashboardService.deleteDashboard(id).subscribe({
        next: () => {
          this.tableData = this.tableData.filter(d => d.id !== id);
          alert('Dashboard deleted successfully.');
        },
        error: () => alert('Delete failed'),
      });
    }
  }

  onBackToManage(): void {
    this.showBlankDashboard = false;
    this.showInteractiveDashboard = false;
  }

  onNewDashboard(): void {
    this.selectedDashboard = null;
    this.showBlankDashboard = true;
    this.showInteractiveDashboard = false;
  }
}


---

✅ 2. Update manage-dashboard.component.html

Add Material icons for edit and delete:

<!-- Inside your <tr *ngFor="let row of tableData"> loop -->

<tr *ngFor="let row of tableData">
  <td *ngFor="let header of tableHeaders">
    <ng-container [ngSwitch]="header.key">
      <span *ngSwitchCase="'createdDate'">{{ row.createdDate | date: 'short' }}</span>
      <span *ngSwitchCase="'modifiedDate'">{{ row.modifiedDate | date: 'short' }}</span>
      <span *ngSwitchCase="'public'">{{ row.public ? 'Yes' : 'No' }}</span>
      <span *ngSwitchCase="'action'">
        <button mat-icon-button color="primary" (click)="onEditDashboard(row)">
          <mat-icon>edit</mat-icon>
        </button>
        <button mat-icon-button color="warn" (click)="onDeleteDashboard(row.id)">
          <mat-icon>delete</mat-icon>
        </button>
      </span>
      <span *ngSwitchDefault>{{ row[header.key] }}</span>
    </ng-container>
  </td>
</tr>


---

✅ 3. Update dashboard.service.ts

Make sure it includes delete and update logic:

deleteDashboard(id: number): Observable<void> {
  return this.http.delete<void>(`${this.apiUrl}/${id}`);
}

updateDashboard(id: number, dashboard: Dashboardd): Observable<Dashboardd> {
  return this.http.put<Dashboardd>(`${this.apiUrl}/${id}`, dashboard);
}


---

✅ 4. Update blank-dashboard.component.ts (example)

If you're reusing the blank dashboard for both creating and editing:

@Input() dashboardData: Dashboardd | null = null;

ngOnInit() {
  if (this.dashboardData) {
    this.form.patchValue(this.dashboardData); // Assuming you use ReactiveForms
  }
}


---

✅ 5. Install Angular Material icons if not done

Run:

npm install @angular/material @angular/cdk

And include Material icons in index.html:

<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">


---

Let me know if you'd like the full updated blank-dashboard code or want help passing the selected dashboard data to it.


blank.dashboard.comp.ts
import { Component, Input, Output, EventEmitter, OnInit } from '@angular/core';
import { DashboardService } from '../dashboard.service';
import { Dashboardd } from '../dashboard.model';

@Component({
  selector: 'app-blank-dashboard',
  templateUrl: './blank-dashboard.component.html',
  styleUrls: ['./blank-dashboard.component.css'],
})
export class BlankDashboardComponent implements OnInit {
  @Input() dashboardData: Dashboardd | null = null;
  @Output() cancelEdit = new EventEmitter<void>();
  @Output() dashboardUpdated = new EventEmitter<void>();

  dashboard: Dashboardd = {
    id: 0,
    name: '',
    description: '',
    public: false,
    createdBy: '',
    createdDate: '',
  };

  constructor(private dashboardService: DashboardService) {}

  ngOnInit(): void {
    if (this.dashboardData) {
      this.dashboard = { ...this.dashboardData };
    }
  }

  save(): void {
    if (this.dashboard.id) {
      // Edit mode
      this.dashboardService.updateDashboard(this.dashboard.id, this.dashboard).subscribe({
        next: () => {
          this.dashboardUpdated.emit();
          this.cancelEdit.emit();
        },
        error: () => alert('Failed to update dashboard')
      });
    } else {
      // New dashboard
      this.dashboardService.addDashboard(this.dashboard).subscribe({
        next: () => {
          this.dashboardUpdated.emit();
          this.cancelEdit.emit();
        },
        error: () => alert('Failed to create dashboard')
      });
    }
  }

  cancel(): void {
    this.cancelEdit.emit();
  }
}

blank-dashboard.comp.html
<div>
  <mat-form-field>
    <input matInput placeholder="Name" [(ngModel)]="dashboard.name">
  </mat-form-field>

  <mat-form-field>
    <textarea matInput placeholder="Description" [(ngModel)]="dashboard.description"></textarea>
  </mat-form-field>

  <mat-checkbox [(ngModel)]="dashboard.public">Public</mat-checkbox>

  <button mat-raised-button color="primary" (click)="save()">Save</button>
  <button mat-raised-button (click)="cancel()">Cancel</button>
</div>

dashboard.service.ts
updateDashboard(id: number, dashboard: Dashboardd): Observable<any> {
  return this.http.put(`${this.apiUrl}/${id}`, dashboard);
}

deleteDashboard(id: number): Observable<void> {
  return this.http.delete<void>(`${this.apiUrl}/${id}`);
}




