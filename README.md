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

[02-06-2025 18:28] Moni: blank-dashboard.component.html

<div class="modal-box">

<div *ngif" showlodal" class="modal-container" (class.fullscreen]="isFullscreen">

<div class="modal-header">

<div class="header-left">

<span class="material-symbols-outlined icon">Dashboard</span>

<h2>{{ formData.name || "New Dashboard' ))</h2>

</div>

<div class="header-actions">

<button (click)""toggle Fullscreen()" title="Fullscreen"></button>

<button (click)="closeModal()" title="Close">X</button>

</div>

</div>

<div class="atep-tracker">

<div "ngfor "let step of steps; let i index" class="step-item" (class.active)=*i currentStep">

<div class="step-circle">{{1+1)}</div>

<span class="step-label">{{ step)}</span>

</div>

<div class="modal-content">

</div>

<-step 1: Initial ->

<form "ngif="currentStep0 #dashboardForm "ngForm" class="form-section">

<div class="form-group">

<label>tName <span class="required">*</span></label>

<input type="text" [(ngModel)]="formData.name" name="name" placeholder="Add a name" required />

</div>

<div class="form-group">

<label>Description</label>

<textarea [(ngModel))""formData.description" name="description" placeholder="Mention description..."></textarea>

</div>

<label>Mark Dashboard As <span class="required">*</span></label> <

<div class="form-group">

div class="radio-options"> <label>

<input type="radio" (ngModel)]="formData.visibility" name="visibility" value="Public" />

<span class="custom-radio"></span> Public

</label>

<input type="radio" [(ngModel)]="formData.visibility" name="visibility" value="Private" />

<label>

<span class="custom-radio"></span> Private

</label>

</div>

<1<div class="checkbox-option">

<label> <input type="checkbox" [ingModel)) "formData.isPublic"/>

<span class="custom-checkbox"></span>MakePublis

</label> </div>-->>

<small>Delect <strong>Private</strong> to assign this dashboard to one of more users or teams</small></div></form>

2: Content

<div "ngIf="currentstep 1" class="content-step" style="display: flex;">

<div class="sidebar" style="flex: 1; padding: irem;">

<h4>Select Card</h4> >

<ul <li [clasa.active)="selectedChart "bar" (click)="setChartType('bar')">Case Queue by Data Element (Bar Chart)</li> 'pie'" (click)="setChartType('pie') ">Case Queue by Data Element (Pie Chart)</li>

<li class.active]="selectedChart

</ul>

</div>

<div class="chart-preview" style="flexi 2; padding: 1rem;">

<ng-container [ngowitch]="selectedChart">

<div "ng@witchCase "bar">

<h3>Bar Chart Preview</h3>

<div class="chart-bar">

<ing [are] "barChartürl" alt="Bar Chart">

</div>

<ATP/>

<div ngawitchCase "pic"

<h3>Pie Chart Preview</h3>

<div class="chart-pie">

<img [arc]="pieChartUrl" alt="Pie Chart">

</div>

</div>

</ng-container

<div class="form-section" style="max-height: 300px; overflow y: auto; margin-top: Zrem;"> <h4>Configure Card: Case Queue by Data Flement of type

selected Chart 'bar'? 'Bar Chart': 'Pie Chart 1)</

<label>Title <span class="required"></span></label>

<input type="text" (ngModel)]="title" name "title" required />

<label>Model <span clase required>*</span></label> <select ((ngModel)]="model" name="model" required

<option *ngfor="let option of modelOptions" (value] "option">{{option}</option>

</select>

<label>Group By <span class="required">></span></label>

<select [(ngModel)]="groupby" name="groupBy" required

<option *ngfor="let group of groupByOptions" [value]="group"> [(group })</option>

</select>

<label>Aggregation</label>

<select ingModel)]="aggregation" name="aggregation">

</select>

<option *ngror "let agy of of aggregationTypes" (value)""aug">{{ agg)]</option>

<label>Aggregation Field</label>

<select (ngModel)]="aggregationrield" name="aggregationField">

<option "ngror "let field of aggregationFields" (value)="field">{{ field ))</option>

</select> <button class="btn add-btn" style="margin-top: 10px;" (click)="addCard()">Add</button>

</div>

</div>

</div>


Step 31 Layout

<div "ngif "currentätep 2 clases content-step">

<div class chart-preview">

<ng-container [ng@witch]"selectedChart">

<div "ngswitchCase "bar'"

<h3>Bar Chart Preview</h3>

<div class="chart-bar chart-container">

<ag-charts [options]"barChartOptions"></ag-charts

</div>

</div>

<div ng@witchCases'ple'">

<h3>Pis Chart Preview</h3>

<div class="chart-pie chart-container">

<ag-charts (options)"pieChartOptions"/ag-charts

</div>

</div>

</ng-container

</div>

</div>

<1- Step 41 Review->

<div "ngif "currentstep3">

<h4>Review & Confirm</h4>

<div classreview-section">

<h5>Step 11 General Info</h5>

<p><strong>Name:</strong> ((formData.name ))</p>

<p><strong>Description:</strong> 1 foamData.description 1 R/A }}</p> <p><strong>Visibility:</strong> {{ formData.visibility)}</p>

<!-- <p><strong>Visibility:</strong> | formats.ispublic 'Phlic'sPrivate" }}</p>

< h5>Step 21 Chart Configuration</h5>

<p><strong>Chart Type:</strong> (selectedChart 'har'? 'Bar Chart 'Pis Chart )}</p>

<p><strong>Title:</strong> ({ title })</p>

<p><strong>Model:</strong> || model }}</p>

<p><strong>Group By:</strong> 11 grouply }}</p>

<p><strong>Aggregation Type:</strong> ( aggregation ))</p> <p><strong>Aggregation Field:</strong> | aggregationField))</p> </div>

<div class="nav-buttona">

<-<button class="btn primary" (click)submit()">Finish</button>>>>

<button nat-raised-button color "primary" (click)="submit Dashboard()">

LeEditMode 7 'Update': 'Create')) Dashboard

</button>

</div>

</div>

</div>

<div class="nav-buttons">

<button class="btn secondary" (click)"prwvStep()" "ngIf="current@tep Back</button> <button class="btn primary" (click)"nexttep() gif *currentStep <3>Nest</button>

</div>

</div>

</div>
[02-06-2025 22:53] Moni: blank-dashboard component.ts

import (Component, Input, EventEmitter, Output) from '@angular/core';

import { getData) from '../////data';

import (FormsModule} from '@angular/forms';

import (CommonModule } from '@angular/common';

import (Router) from '@angular/router';

import (AgChartsModule) from "ag-charts-angular"; import (AgChartoptions) from 'ag-charts-community';

import (DashboardService) from '../dashboard.service';

import (Dashboardd } from '../dashboard.model';

// Add Input decorator

@Component({

selector: 'app-blank-dashboard',

standalone: true,

imports: [FormsModule, CommonModule, AgChartsModule),

templateUrl: './blank-dashboard.component.html',

styleUrls: ['./blank-dashboard.component.css'],

13

export class BlankDashboardComponent {

@Input() dashboardToEdit: any; // Input from manage-dashboard

@Output() dashboardClose new EventEmitter<void>();

@Input() editData?: Dashboardd;

showModal = true;

isFullscreen = false;

currentStep = 0;

steps = ['Initial', 'Content', 'Layout', 'Review'];

formData = (

name:'",

description:"",

visibility: 'Public'

}; selectedChart = 'bar';

title = '';

model";
groupBy="";

aggregation = "";

aggregationField = "";

modelOptions = ['Germany_Holdings', 'Luxembourg_Holdings", "Monacco_Holdings']:

groupByOptions = ['Amount', 'Case Id', 'Create Date', 'Custom Value'];

aggregationTypes = ['Count', 'Sum', 'Average', 'Max', 'Min'];

aggregationFields = ['Total Amount', 'Case Number', 'Score'];

barChartOptions: AgChartOptions = {

data: getData(),

series: this.modelOptions.map(model =>({

type: "bar" as const,

xKey: "quarter",

ykey: model,

yName: model,

})),

pieChartOptions: AgChartOptions = {

data: getData(),

title: (

text: "Portfolio Composition", 1,

series: [

type: "pie",

sectorLabelKey: "Amount", sectorLabel: (

۱۰

angleKey: "Amount", calloutLabelKey: "quarter", color: "white", fontWeight: "bold", formatter: ({ value }) => $$((value/1000).toFixed (0))K', 
},
},
],
};
barchartUrl: string;

piechartUrl: string;

form: any:

constructor (private router: Router, private dashboardservice: DashboardService) (

this.barChartUrl = 'https://isuite-evaluation.dev.echonet/ISUITE/NextGen/assets/barchart.png" this.pieChartUrl = 'https://isuite-evaluation.dev.echonet/ISUITE/NextGen/assets/piechart.png":

toggleFullscreen() {

this.isFullscreen Ithis.isFullscreen;

closeModal() {

this.dashboardClose.emit();

nextStep(){

if (this.currentStep 0 && !this.formData.name.trim()) {

alert('Please fill in the required "Name" field.');

return;

if (this.currentStep < this.steps.length-1) {

this.currentStep++;

}

prevStep() {

if (this.currentStep > 0) (

this.currentStep--;

setChartType (type: string): void (

this.selectedChart type;

this.title= "Case Queue by Data Element of type $(type === 'bar'? 'Bar Chart': 'Pie Chart'}';
addCard(): void {

// Validation logic and storing form values

console.log('Card added:', {

chartType: this.selectedChart,

title: this.title,

model: this.model,

groupBy: this.groupBy,

aggregationField: this.aggregationField

});

}

ngOnInit() {

if (this.editData) {

this.isEditMode = true;

// Pre-fill the form with existing dashboard data

this.formData = {

name: this.editData.name?.toString() || '",

description: this.editData.description,

visibility: this.editData.isPublic? 'Public': 'Private' };

this.selectedChart = this.editData.chartType;

this.model = this.editData.model;

this.groupBy = this.editData.groupBy;

this.aggregation = this.editData.aggregation;

this.aggregationField = this.editData.aggregationField;

}
isEditMode = false;

submit Dashboard(): void {

const dashboardPayload: Dashboardd = {

name: this.formData.name,

description: this.formData.description,

isPublic: this.formData.visibility = 'Public',

chartType: this.selectedChart,

model: this.model,

groupBy: this.groupBy,

aggregation: this.aggregation,

aggregationField: this.aggregationField,

public: this.formData.visibility 'Public',

createdBy: this.editData?.createdBy || 'h59606', // fallback if new

createdDate: this.editData?.createdDate || new Date().toISOString(),

modifiedDate: new Date().toISOString(),

modifiedBy: this.isEditMode ? 'h59606': undefined

};

if (this.isEditMode && this.editData?.id) {

// Update existing dashboard

this.dashboardService.updateDashboard (this.editData.id, dashboard Payload).subscribe ((

next: () => {

console.log('Dashboard updated');

this.dashboardClose.emit();

1,

error: (err) => console.error('Update failed', err)

});

} else {

// Create new dashboard

this.dashboardService.addDashboard (dashboard Payload).subscribe({

next: () => {

console.log('Dashboard created');

this.dashboardClose.emit();

},

error: (err) => console.error('Update failed', err)

});

} else {

// Create new dashboard

this.dashboardService.addDashboard (dashboardPayload).subscribe({

next: () => {

console.log('Dashboard created');

this.dashboardClose.emit();

},

error: (err) => console.error('Create failed', err)

});

}}
[02-06-2025 23:03] Moni: manage-dashboard.ts

import { Component, EventEmitter, Output } from '@angular/core';

import (Dashboardservice) from './dashboard.service';

import (NgIf } from '@angular/common';

import { CommonModule } from '@angular/common';

import (OnInit) from '@angular/core';

import (InteractiveDashboard Component } from './interactive-dashboard/interactive-dashboard.component';

import (BlankDashboardComponent } from './blank-dashboard/blank-dashboard.component';

import { Dashboardd } from './dashboard.model';

import (MatIconModule } from '@angular/material/icon';

import (MatButtonModule } from '@angular/material/button';

@Component({

selector: 'app-manage-dashboard',

imports: [MatIconModule, MatButtonModule, BlankDashboardComponent, InteractiveDashboardComponent, NgIf, CommonModule),

templateUrl: './manage-dashboard.component.html',

styleUrl: './manage-dashboard.component.css'

})

export class ManageDashboardComponent (

tableData: Dashboardd[] = [];

selectedDashboard: Dashboardd | null = null;

dashboards = [

id: 'blank',

name: 'Blank Dashboard',

icon: '',

description: 'Start with a blank canvas'

id: 'interactive',

name: 'Interactive Dashboard',

icon: '',

description: 'Pre-built interactive components'

}

];

D

tableHeaders=[

(key: 'name', label: 'Name'),

(key: 'description', label: 'Description'},

(key: 'createdBy', label: 'Created By'),

{key: 'createdDate', label: 'Created Date'),

{key: 'modifiedBy', label: 'Modified By'),

{key: 'modifiedDate', label: 'Modified Date'),

{key: 'public', label: 'Public'},

(key: 'action', label: 'Action'},

1;

constructor (private dashboardService: DashboardService) {}

@Output() closeDashboard = new EventEmitter<void>();

@Output() selectDashboard = new EventEmitter<string>();

showBlankDashboard = false;

showInteractiveDashboard = false;

ngOnInit():void {

this.loadDashboards();

}

loadDashboards() {

this.dashboardservice.getDashboards().subscribe({ next: (data) => this.tableData = data, error: () => alert('Failed to load dashboards') });

}

onClose():void {

this.closeDashboard.emit();

onSelect Dashboard (dashboardType: string):void {

if (dashboardType 'blank') {

this.showBlankDashboard=true;

this.showInteractiveDashboard=false;

else if (dashboardType == 'interactive') { this.showInteractiveDashboard=true;
this.showBlankDashboard=false; )

this.selectDashboard.emit (dashboardType);

onBackToManage () {

this.showBlankDashboard=false; this.showInteractiveDashboard=false; this.selectedDashboardData=null;

}

onNewDashboard(): void { this.selectedDashboard = null; this.showBlankDashboard = true; this.showInteractiveDashboard = false;

}

onEdit Dashboard (dashboard: any): void (

this.selectedDashboardData = dashboard;

this.showBlankDashboard = true;

this.showInteractiveDashboard = false;

}

selectedDashboardData: any null;

onDelete Dashboard (id: number): void (

if (confirm('Are you sure you want to delete this dashboard?')) {

this.dashboardService.deleteDashboard(id).subscribe (( next: () => { this.tableData = this.tableData.filter (d => d.id != id); alert('Dashboard deleted successfully.');

error: () => alert('Delete failed'), });
}}}
[02-06-2025 23:07] Moni: managa dashboard comp html
[02-06-2025 23:09] Moni: + New

<div class="manage-dashboard-container">

<!-- Main Manage Dashboard View -->

<div *ngIf="showBlankDashboard && showInteractiveDashboard">

<!-- Header -->

<div class="header">

<h2 class="title">Manage Dashboard</h2>

<button class="close-btn" (click)="onClose()">x</button>

</div>

<!-- New Dashboard Button -->

<div class="new-dashboard-section">

<button class="new-dashboard-btn" (click) ="onNewDashboard()">

<span class="plus-icon">+</span>

New Dashboard

</button>

</div>

<!-- Dashboard Types ->

<div class="dashboard-types">

<div

class="dashboard-card"

*ngFor "let dashboard of dashboards"

(click)="onSelect Dashboard (dashboard.id)"

<div class="dashboard-icon">{(dashboard.icon}}</div>

<div class="dashboard-name">{{dashboard.name}}</div>

</div>

</div>

<!-- All Dashboards Section -->

<div class="all-dashboards-section">

<h3 class="section-title">All Dashboards</h3>

<!-- Table -->

<div class="table-container">

<table class="dashboards-table">

<thead>
[02-06-2025 23:09] Moni: <tbody>

<tr *ngIf="tableData.length === 0" class="no-data-row">

<td [attr.colspan]="tableHeaders.length" class="no-data-cell">

No Rows To Show

</td>

</tr>

<tr *ngFor="let row of tableData">

<td *ngfor="let header of tableHeaders">

<ng-container [ngswitch)="header.key">

<span ngawitchCase="'createdDate'">{{ row.createdDate date: 'short' })</span>

<span *ngswitchCase="'modifiedDate">{{ row.modifiedDate date: 'short')}</span>

<span *ngswitchCase="'public'">((row.public ? 'Yes': 'No' }}</span>

<span *ngswitchCase="'action'">

<button mat-icon-button color="primary" (click)="onEdit Dashboard (row) ">

<mat-icon>edit</mat-icon>

</button>

<button mat-icon-button color="warn" (click)="onDelete Dashboard (row.idl)">

<mat-icon>delete</mat-icon>

</button>

</span>

<span "ngäwitchDefault>((row[header.key]))</span>

</ng-container>

</td>

</tr>

</tbody>

</table>

</div>

</div>

</div>

<!-- Blank Dashboard View -->

<div "ngIf="showBlank Dashboard">

<app-blank-dashboard

[editData] = "selectedDashboardData" (dashboardClose) ="onBackToManage ()"></app-blank-dashboard>

</div>
<--Interactive Dashboard View -->

<div "ngIf="showInteractiveDashboard" class="dashboard-view">

<div class="dashboard-header">

<button class="back-btn" (click)="onBackToManage ()">- Back to Manage</button>

<button class="close-btn" (click)="onClose ()">×</button>

</div>

<!-- Add your interactive dashboard component here-->

<app-interactive-dashboard> </app-interactive-dashboard>

<div class="placeholder">Interactive Dashboard Component will be rendered here</div>

</div>
------------------------------------------------------------------------------------------------
