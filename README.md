## I. Analyze and determine system requirements
## I.1. Actors

| No. | Actor            | Main Responsibilities                                                                                  |
| --: | ---------------- | ------------------------------------------------------------------------------------------------------ |
|   1 | **System admin** | Manage user accounts, roles, permissions, system settings, and audit logs.                             |
|   2 | **HR Staff**     | Manage employees, departments, positions, recruitment, onboarding, leave, and HR reports.              |
|   3 | **Manager**      | Manage team members, assign tasks, approve timesheets, approve leave requests, and review performance. |
|   4 | **Staff**     | Clock in/out, track working time, submit timesheets, request leave, and manage assigned tasks.         |
|   5 | **Client**    | Follow team assigned, the project schedule, payments and history                   |
|   6 | **Candidate**    | Apply for job openings, submit personal information, and track application status.                     |
|   7 | **Third party**    | Email service, cloud storage, calendar, payroll, payment gateway                   |
|   8 | **Tentant admin**    | Represents an organization or company using the platform, with its own users, employees, departments, settings, and isolated data. |

## I.2. Functionalites

## Workforce Management System Mindmap

```mermaid
flowchart LR
    %% =====================================================
    %% NODE DECLARATIONS
    %% Each node is declared exactly once
    %% =====================================================

    WMS["Workforce Management System<br/>(BambooHR + Hubstaff)"]:::rootStyle

    %% =====================================================
    %% LEFT-SIDE MAIN BRANCHES
    %% =====================================================

    UserAccessSecurity["**User Access & Security**"]:::highlightSecurity
    EmployeeOrganization["**Employee & Organization**"]:::highlightEmployee
    TimeAttendance["**Time & Attendance**"]:::highlightAttendance
    LeaveScheduling["**Leave & Scheduling**"]:::highlightLeave

    %% -----------------------------------------------------
    %% User Access & Security
    %% -----------------------------------------------------

    Authentication["Authentication"]:::categoryStyle
    Authorization["Authorization"]:::categoryStyle
    AccountManagement["Account Management"]:::categoryStyle

    %% Login["Login"]
    %% Logout["Logout"]:::priorityFeature
    %% ForgotResetPassword["Forgot / Reset Password"]:::normalFeature
    %% RefreshToken["Refresh Token"]:::normalFeature

    %% RoleManagement["Role Management"]:::priorityFeature
    %% PermissionManagement["Permission Management"]:::normalFeature
    %% RoleAssignment["Role Assignment"]:::normalFeature

    %% UserProfile["User Profile"]:::priorityFeature
    %% AccountActivation["Activate / Deactivate Account"]:::priorityFeature
    %% ChangePassword["Change Password"]:::normalFeature

    %% -----------------------------------------------------
    %% Employee & Organization
    %% -----------------------------------------------------

    EmployeeManagement["Employee Management"]:::categoryStyle
    OrganizationManagement["Organization Management"]:::categoryStyle
    EmploymentManagement["Employment Management"]:::categoryStyle

    EmployeeProfile["Employee Profile"]:::normalFeature
    EmployeeContact["Contact Information"]:::normalFeature
    EmployeeDocuments["Employee Documents"]:::normalFeature
    EmergencyContact["Emergency Contact"]:::normalFeature

    DepartmentManagement["Department Management"]:::priorityFeature
    PositionManagement["Position Management"]:::priorityFeature
    TeamManagement["Team Management"]:::normalFeature
    ReportingLine["Manager Reporting Line"]:::priorityFeature

    EmploymentContract["Employment Contract"]:::normalFeature
    EmploymentStatus["Employment Status"]:::normalFeature
    CompensationInfo["Compensation Information"]:::normalFeature
    WorkLocation["Work Location"]:::normalFeature

    %% -----------------------------------------------------
    %% Time & Attendance
    %% -----------------------------------------------------

    AttendanceTracking["Attendance Tracking"]:::categoryStyle
    TimesheetManagement["Timesheet Management"]:::priorityFeature
    AttendanceApproval["Attendance Approval"]:::categoryStyle

    ClockIn["Clock In"]:::priorityFeature
    ClockOut["Clock Out"]:::priorityFeature
    BreakTracking["Break Tracking"]:::priorityFeature
    AttendanceRecord["Attendance Record"]:::priorityFeature

    DailyTimesheet["Daily Timesheet"]:::priorityFeature
    WeeklyTimesheet["Weekly Timesheet"]:::priorityFeature
    ManualTimeEntry["Manual Time Entry"]:::normalFeature
    TimesheetCorrection["Timesheet Correction"]:::normalFeature

    SubmitTimesheet["Submit Timesheet"]:::priorityFeature
    ApproveTimesheet["Approve Timesheet"]:::priorityFeature
    RejectTimesheet["Reject Timesheet"]:::priorityFeature
    AttendanceException["Attendance Exception"]:::normalFeature

    %% -----------------------------------------------------
    %% Leave & Scheduling
    %% -----------------------------------------------------

    LeaveManagement["Leave Management"]:::priorityFeature
    WorkSchedule["Work Schedule"]:::categoryStyle
    ShiftManagement["Shift Management"]:::categoryStyle

    LeaveType["Leave Type"]:::normalFeature
    LeaveBalance["Leave Balance"]:::priorityFeature
    LeaveRequest["Leave Request"]:::priorityFeature
    LeaveApproval["Leave Approval"]:::priorityFeature

    WorkCalendar["Work Calendar"]:::normalFeature
    HolidayManagement["Holiday Management"]:::normalFeature
    WorkingDayRule["Working Day Rule"]:::normalFeature
    EmployeeSchedule["Employee Schedule"]:::normalFeature

    ShiftDefinition["Shift Definition"]:::normalFeature
    ShiftAssignment["Shift Assignment"]:::normalFeature
    ShiftSwap["Shift Swap"]:::normalFeature
    OvertimeRequest["Overtime Request"]:::normalFeature

    %% =====================================================
    %% RIGHT-SIDE MAIN BRANCHES
    %% =====================================================

    ProjectProductivity["**Project & Productivity**"]:::highlightProject
    RecruitmentOnboarding["**Recruitment & Onboarding**"]:::highlightRecruitment
    PerformanceDevelopment["**Performance & Development**"]:::highlightPerformance
    AdministrationReporting["**Administration & Reporting**"]:::highlightAdmin

    %% -----------------------------------------------------
    %% Project & Productivity
    %% -----------------------------------------------------

    ProjectManagement["Project Management"]:::priorityFeature
    TaskManagement["Task Management"]:::priorityFeature
    ProductivityTracking["Productivity Tracking"]:::priorityFeature
    ProjectCostManagement["Project Cost Management"]:::categoryStyle

    CreateProject["Create Project"]:::priorityFeature
    ProjectMember["Project Member"]:::priorityFeature
    ProjectStatus["Project Status"]:::priorityFeature
    ProjectBudget["Project Budget"]:::normalFeature

    CreateTask["Create Task"]:::priorityFeature
    AssignTask["Assign Task"]:::priorityFeature
    TaskPriority["Task Priority"]:::priorityFeature
    TaskDeadline["Task Deadline"]:::priorityFeature

    TaskTimer["Task Timer"]:::priorityFeature
    ActivitySummary["Activity Summary"]:::normalFeature
    IdleTime["Idle Time"]:::normalFeature
    ProductivityReport["Productivity Report"]:::priorityFeature

    HourlyRate["Hourly Rate"]:::normalFeature
    ApprovedHours["Approved Hours"]:::normalFeature
    LaborCost["Labor Cost"]:::normalFeature
    BudgetAlert["Budget Alert"]:::normalFeature

    %% -----------------------------------------------------
    %% Recruitment & Onboarding
    %% -----------------------------------------------------

    RecruitmentManagement["Recruitment Management"]:::priorityFeature
    CandidateManagement["Candidate Management"]:::priorityFeature
    InterviewManagement["Interview Management"]:::categoryStyle
    OnboardingManagement["Onboarding Management"]:::priorityFeature

    JobOpening["Job Opening"]:::normalFeature
    JobDescription["Job Description"]:::normalFeature
    HiringTeam["Hiring Team"]:::normalFeature
    RecruitmentStatus["Recruitment Status"]:::normalFeature

    CandidateProfile["Candidate Profile"]:::normalFeature
    JobApplication["Job Application"]:::normalFeature
    ResumeManagement["Resume Management"]:::normalFeature
    CandidatePipeline["Candidate Pipeline"]:::normalFeature

    InterviewSchedule["Interview Schedule"]:::normalFeature
    InterviewFeedback["Interview Feedback"]:::normalFeature
    InterviewResult["Interview Result"]:::normalFeature
    OfferManagement["Offer Management"]:::normalFeature

    OnboardingChecklist["Onboarding Checklist"]:::priorityFeature
    DocumentCollection["Document Collection"]:::priorityFeature
    EquipmentAssignment["Equipment Assignment"]:::priorityFeature
    OnboardingProgress["Onboarding Progress"]:::priorityFeature

    %% -----------------------------------------------------
    %% Performance & Development
    %% -----------------------------------------------------

    GoalManagement["Goal Management"]:::priorityFeature
    PerformanceReview["Performance Review"]:::categoryStyle
    FeedbackManagement["Feedback Management"]:::categoryStyle
    LearningDevelopment["Learning & Development"]:::categoryStyle

    EmployeeGoal["Employee Goal"]:::priorityFeature
    TeamGoal["Team Goal"]:::priorityFeature
    GoalProgress["Goal Progress"]:::priorityFeature
    GoalStatus["Goal Status"]:::priorityFeature

    ReviewCycle["Review Cycle"]:::normalFeature
    SelfAssessment["Self Assessment"]:::normalFeature
    ManagerAssessment["Manager Assessment"]:::normalFeature
    PerformanceRating["Performance Rating"]:::normalFeature

    ManagerFeedback["Manager Feedback"]:::normalFeature
    PeerFeedback["Peer Feedback"]:::normalFeature
    OneOnOneNote["One-on-One Note"]:::normalFeature
    Recognition["Employee Recognition"]:::normalFeature

    TrainingCourse["Training Course"]:::normalFeature
    CourseAssignment["Course Assignment"]:::normalFeature
    SkillTracking["Skill Tracking"]:::normalFeature
    DevelopmentPlan["Development Plan"]:::normalFeature

    %% -----------------------------------------------------
    %% Administration & Reporting
    %% -----------------------------------------------------

    DashboardManagement["Dashboard Management"]:::categoryStyle
    ReportingManagement["Reporting Management"]:::categoryStyle
    NotificationManagement["Notification Management"]:::categoryStyle
    SystemAdministration["System Administration"]:::categoryStyle

    EmployeeDashboard["Employee Dashboard"]:::priorityFeature
    ManagerDashboard["Manager Dashboard"]:::priorityFeature
    HRDashboard["HR Dashboard"]:::priorityFeature
    AdminDashboard["Admin Dashboard"]:::priorityFeature

    EmployeeReport["Employee Report"]:::priorityFeature
    AttendanceReport["Attendance Report"]:::priorityFeature
    LeaveReport["Leave Report"]:::normalFeature
    ProjectReport["Project Report"]:::normalFeature

    InAppNotification["In-App Notification"]:::normalFeature
    EmailNotification["Email Notification"]:::normalFeature
    ApprovalReminder["Approval Reminder"]:::normalFeature
    DeadlineReminder["Deadline Reminder"]:::normalFeature

    SystemConfiguration["System Configuration"]:::normalFeature
    AuditLog["Audit Log"]:::normalFeature
    DataImport["Data Import"]:::normalFeature
    DataExport["Data Export"]:::normalFeature

    %% =====================================================
    %% CONNECTIONS
    %% Connections contain node IDs only
    %% =====================================================

    %% -----------------------------------------------------
    %% Left-side branches point toward WMS
    %% -----------------------------------------------------

    UserAccessSecurity --> WMS
    EmployeeOrganization --> WMS
    TimeAttendance --> WMS
    LeaveScheduling --> WMS

    %% User Access & Security

    Authentication --> UserAccessSecurity
    Authorization --> UserAccessSecurity
    AccountManagement --> UserAccessSecurity

    %% Login --> Authentication
    %% Logout --> Authentication
    %% ForgotResetPassword --> Authentication
    %% RefreshToken --> Authentication

    %% RoleManagement --> Authorization
    %% PermissionManagement --> Authorization
    %% RoleAssignment --> Authorization

    %% UserProfile --> AccountManagement
    %% AccountActivation --> AccountManagement
    %% ChangePassword --> AccountManagement

    %% Employee & Organization

    EmployeeManagement --> EmployeeOrganization
    OrganizationManagement --> EmployeeOrganization
    EmploymentManagement --> EmployeeOrganization

    EmployeeProfile --> EmployeeManagement
    EmployeeContact --> EmployeeManagement
    EmployeeDocuments --> EmployeeManagement
    EmergencyContact --> EmployeeManagement

    DepartmentManagement --> OrganizationManagement
    PositionManagement --> OrganizationManagement
    TeamManagement --> OrganizationManagement
    ReportingLine --> OrganizationManagement

    EmploymentContract --> EmploymentManagement
    EmploymentStatus --> EmploymentManagement
    CompensationInfo --> EmploymentManagement
    WorkLocation --> EmploymentManagement

    %% Time & Attendance

    AttendanceTracking --> TimeAttendance
    TimesheetManagement --> TimeAttendance
    AttendanceApproval --> TimeAttendance

    ClockIn --> AttendanceTracking
    ClockOut --> AttendanceTracking
    BreakTracking --> AttendanceTracking
    AttendanceRecord --> AttendanceTracking

    DailyTimesheet --> TimesheetManagement
    WeeklyTimesheet --> TimesheetManagement
    ManualTimeEntry --> TimesheetManagement
    TimesheetCorrection --> TimesheetManagement

    SubmitTimesheet --> AttendanceApproval
    ApproveTimesheet --> AttendanceApproval
    RejectTimesheet --> AttendanceApproval
    AttendanceException --> AttendanceApproval

    %% Leave & Scheduling

    LeaveManagement --> LeaveScheduling
    WorkSchedule --> LeaveScheduling
    ShiftManagement --> LeaveScheduling

    LeaveType --> LeaveManagement
    LeaveBalance --> LeaveManagement
    LeaveRequest --> LeaveManagement
    LeaveApproval --> LeaveManagement

    WorkCalendar --> WorkSchedule
    HolidayManagement --> WorkSchedule
    WorkingDayRule --> WorkSchedule
    EmployeeSchedule --> WorkSchedule

    ShiftDefinition --> ShiftManagement
    ShiftAssignment --> ShiftManagement
    ShiftSwap --> ShiftManagement
    OvertimeRequest --> ShiftManagement

    %% -----------------------------------------------------
    %% Right-side branches point outward from WMS
    %% -----------------------------------------------------

    WMS --> ProjectProductivity
    WMS --> RecruitmentOnboarding
    WMS --> PerformanceDevelopment
    WMS --> AdministrationReporting

    %% Project & Productivity

    ProjectProductivity --> ProjectManagement
    ProjectProductivity --> TaskManagement
    ProjectProductivity --> ProductivityTracking
    ProjectProductivity --> ProjectCostManagement

    ProjectManagement --> CreateProject
    ProjectManagement --> ProjectMember
    ProjectManagement --> ProjectStatus
    ProjectManagement --> ProjectBudget

    TaskManagement --> CreateTask
    TaskManagement --> AssignTask
    TaskManagement --> TaskPriority
    TaskManagement --> TaskDeadline

    ProductivityTracking --> TaskTimer
    ProductivityTracking --> ActivitySummary
    ProductivityTracking --> IdleTime
    ProductivityTracking --> ProductivityReport

    ProjectCostManagement --> HourlyRate
    ProjectCostManagement --> ApprovedHours
    ProjectCostManagement --> LaborCost
    ProjectCostManagement --> BudgetAlert

    %% Recruitment & Onboarding

    RecruitmentOnboarding --> RecruitmentManagement
    RecruitmentOnboarding --> CandidateManagement
    RecruitmentOnboarding --> InterviewManagement
    RecruitmentOnboarding --> OnboardingManagement

    RecruitmentManagement --> JobOpening
    RecruitmentManagement --> JobDescription
    RecruitmentManagement --> HiringTeam
    RecruitmentManagement --> RecruitmentStatus

    CandidateManagement --> CandidateProfile
    CandidateManagement --> JobApplication
    CandidateManagement --> ResumeManagement
    CandidateManagement --> CandidatePipeline

    InterviewManagement --> InterviewSchedule
    InterviewManagement --> InterviewFeedback
    InterviewManagement --> InterviewResult
    InterviewManagement --> OfferManagement

    OnboardingManagement --> OnboardingChecklist
    OnboardingManagement --> DocumentCollection
    OnboardingManagement --> EquipmentAssignment
    OnboardingManagement --> OnboardingProgress

    %% Performance & Development

    PerformanceDevelopment --> GoalManagement
    PerformanceDevelopment --> PerformanceReview
    PerformanceDevelopment --> FeedbackManagement
    PerformanceDevelopment --> LearningDevelopment

    GoalManagement --> EmployeeGoal
    GoalManagement --> TeamGoal
    GoalManagement --> GoalProgress
    GoalManagement --> GoalStatus

    PerformanceReview --> ReviewCycle
    PerformanceReview --> SelfAssessment
    PerformanceReview --> ManagerAssessment
    PerformanceReview --> PerformanceRating

    FeedbackManagement --> ManagerFeedback
    FeedbackManagement --> PeerFeedback
    FeedbackManagement --> OneOnOneNote
    FeedbackManagement --> Recognition

    LearningDevelopment --> TrainingCourse
    LearningDevelopment --> CourseAssignment
    LearningDevelopment --> SkillTracking
    LearningDevelopment --> DevelopmentPlan

    %% Administration & Reporting

    AdministrationReporting --> DashboardManagement
    AdministrationReporting --> ReportingManagement
    AdministrationReporting --> NotificationManagement
    AdministrationReporting --> SystemAdministration

    DashboardManagement --> EmployeeDashboard
    DashboardManagement --> ManagerDashboard
    DashboardManagement --> HRDashboard
    DashboardManagement --> AdminDashboard

    ReportingManagement --> EmployeeReport
    ReportingManagement --> AttendanceReport
    ReportingManagement --> LeaveReport
    ReportingManagement --> ProjectReport

    NotificationManagement --> InAppNotification
    NotificationManagement --> EmailNotification
    NotificationManagement --> ApprovalReminder
    NotificationManagement --> DeadlineReminder

    SystemAdministration --> SystemConfiguration
    SystemAdministration --> AuditLog
    SystemAdministration --> DataImport
    SystemAdministration --> DataExport

    %% =====================================================
    %% STYLE DEFINITIONS
    %% =====================================================

    classDef rootStyle fill:#1d3557,stroke:#457b9d,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:17px;

    %% Main left-side branches

    classDef highlightSecurity fill:#31c83b,stroke:#149b24,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:15px;
    classDef highlightEmployee fill:#86d800,stroke:#62a800,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:15px;
    classDef highlightAttendance fill:#ffc51b,stroke:#e5a900,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:15px;
    classDef highlightLeave fill:#ffa000,stroke:#e48600,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:15px;

    %% Main right-side branches

    classDef highlightProject fill:#4169e1,stroke:#234fcb,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:15px;
    classDef highlightRecruitment fill:#9569e8,stroke:#7146c7,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:15px;
    classDef highlightPerformance fill:#ff4f87,stroke:#d92d68,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:15px;
    classDef highlightAdmin fill:#ff3d14,stroke:#d92806,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:15px;


    %% Feature styles
    %% Normal features use a neutral white/gray style.
    classDef normalFeature fill:#ffffff,stroke:#b0bec5,stroke-width:1.5px,color:#37474f;

    %% High-priority features are highlighted.
    classDef priorityFeature fill:#fff3cd,stroke:#ff9800,stroke-width:3px,color:#7a4b00,font-weight:bold;

    %% Intermediate categories remain neutral.
    classDef categoryStyle fill:#f5f7f9,stroke:#90a4ae,stroke-width:2px,color:#37474f,font-weight:bold;
```

## High-Priority Features to Implement First

The following features are ordered by business impact and represent the core value of a system combining BambooHR and Hubstaff.
| No. | Feature                                  | Impact   | Short Description                                                                                      |
| --: | ---------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------ |
|   1 | Project and Task Time Tracking           | Critical | Track how much time employees spend working on assigned projects and tasks.                            |
|   2 | Payroll Processing                       | Critical | Calculate employee earnings, deductions, allowances, overtime, and net salary for each payroll period. |
|   3 | Payslip Management                       | Critical | Generate, publish, view, and download employee payslips.                                               |
|   4 | Clock In / Clock Out                     | Critical | Record when employees start and finish their working sessions.                                         |
|   5 | Break Tracking                           | Critical | Record employee break start time, end time, and total break duration.                                  |
|   6 | Attendance Record Management             | Critical | Store and manage daily attendance records, working hours, absences, and attendance status.             |
|   7 | Overtime Management                      | Critical | Record, request, approve, and calculate employee overtime.                                             |
|   8 | Timesheet Management                     | Critical | Summarize employee working time by day, week, project, and task.                                       |
|   9 | Timesheet Review and Approval            | Critical | Allow managers to review, approve, reject, or request corrections to employee timesheets.              |
|  10 | Onboarding management         | Critical | Create onsite job locations, assign employees and schedules, and verify attendance using GPS or geofencing. |
|  11 | Employment Lifecycle Management          | Critical | Manage employee onboarding status, probation, activation, transfer, suspension, and termination.       |
|  12 | Leave Request Management                 | Critical | Allow employees to submit, update, cancel, and view leave requests.                                    |
|  13 | Leave Balance Management                 | Critical | Track employee leave entitlement, usage, adjustments, and remaining balance.                           |
|  14 | Leave Approval                           | Critical | Allow managers or HR staff to approve or reject employee leave requests.                               |
|  15 | Project Management                       | High     | Create, update, archive, and track projects and their current status.                                  |
|  16 | Project Member Management                | High     | Add, remove, and assign employees to projects with project-specific responsibilities.                  |
|  17 | Task Management                          | High     | Create, update, prioritize, assign, and monitor tasks within projects.                                 |
|  18 | Task Progress Management                 | High     | Track task status, completion percentage, deadlines, and overdue work.                                 |
|  19 | Department Management                    | High     | Create and manage departments and assign department managers.                                          |
|  20 | Position Management                      | High     | Define job positions, titles, responsibilities, and position status.                                   |
|  21 | Team and Reporting Line Management       | High     | Organize employees into teams and define manager–employee reporting relationships.                     |
|  22 | Workforce Dashboard                      | High     | Display role-specific summaries for employees, attendance, payroll, leave, projects, and tasks.        |
|  23 | Workforce Reporting and Export           | High     | Generate and export payroll, attendance, timesheet, leave, project, and employee reports.              |
|  24 | Tenant Management                        | High     | Create and manage organizations while keeping each tenant’s users and business data isolated.          |
|  25 | Tenant Configuration                     | High     | Manage tenant-specific work schedules, leave policies, payroll settings, and system preferences.       |
|  26 | Employee Experience and Engagement      | High   | Publish company announcements, collect employee feedback, run satisfaction surveys, and monitor employee wellbeing and engagement.          |
|  27 | Compensation Planning and Total Rewards | High   | Plan salary adjustments, benchmark compensation, manage compensation cycles, budgets, approvals, and employee total rewards statements.     |
|  28 | Productivity and Activity Monitoring    | High   | Track activity levels, active and idle time, workload patterns, utilization, and productivity trends during recorded work sessions.         |
|  29 | Screenshot, App, and URL Tracking       | High   | Capture optional work screenshots and record applications and websites used while employees track time, with configurable privacy controls. |


## II. Use Case Images

### Core Time, Attendance, and Leave

### 1. Project and Time Tracking
![Project and Time Tracking](workforce-management/docs/usecases/uc01-project-and-time-tracking/uc01-project-and-time-tracking.png)

### 2. Payroll Processing
![Payroll Processing](workforce-management/docs/usecases/uc02-payroll-processing/uc02-payroll-processing.png)

### 3. Payslip Management
![Payslip Management](workforce-management/docs/usecases/uc03-payslip-management/uc03-payslip-management.png)

### 4. Clock In / Clock Out
![Clock In / Clock Out](workforce-management/docs/usecases/uc04-clock-in-or-out/uc04-clock-in-or-out.png)

### 5. Break Tracking
![Break Tracking](workforce-management/docs/usecases/uc05-break-tracking/uc05-break-tracking.png)

### 6. Attendance Record Management
![Attendance Record Management](workforce-management/docs/usecases/uc-06-attendance-record-management/uc-06-attendance-record-management.png)

### 7. Overtime Management
![Overtime Management](workforce-management/docs/usecases/uc-07-overtime-management/uc-07-overtime-management.png)

### 8. Timesheet Management
![Timesheet Management](workforce-management/docs/usecases/uc-08-timesheet-management/uc-08-timesheet-management.png)

### 9. Time Review and Approval
![Time Review and Approval](workforce-management/docs/usecases/uc-09-time-review-and-approval/uc-09-time-review-and-approval.png)

### 10. Onsite Work Location Management
![Onsite Work Location Management](workforce-management/docs/usecases/uc10-onsite-work-location-management/uc10-onsite-work-location-management.png)

### 11. Employment Lifecycle Management
![Employment Lifecycle Management](workforce-management/docs/usecases/uc-11-employement-liftcycle-management/uc-11-employement-liftcycle-management.png)

### 12. Leave Request Management
![Leave Request Management](workforce-management/docs/usecases/uc-12-leave-request-management/uc-12-leave-request-management.png)

### 13. Leave Balance Management
![Leave Balance Management](workforce-management/docs/usecases/uc-13-leave-balance-management/uc-13-leave-balance-management.png)

### 14. Leave Approval
![Leave Approval](workforce-management/docs/usecases/uc-14-leave-approval/uc-14-leave-approval.png)

### Project, Task, and Productivity

### 15. Project Management
![Project Management](workforce-management/docs/usecases/uc-15-project-management/uc-15-project-management.png)

### 16. Project Member Management
![Project Member Management](workforce-management/docs/usecases/uc-16-project-member-management/uc-16-project-member-management.png)

### 17. Task Management
![Task Management](workforce-management/docs/usecases/uc-17-task-management/uc-17-task-management.png)

### 18. Task Progress Management
![Task Progress Management](workforce-management/docs/usecases/uc-18-task-progress-mangament/uc-18-task-progress-mangament.png)

### 19. Department Management
![Department Management](workforce-management/docs/usecases/uc-19-department-management/uc-19-department-management.png)

### 20. Position Management
![Position Management](workforce-management/docs/usecases/uc-20-position-management/uc-20-position-management.png)

### 21. Team and Reporting Line Management
![Team and Reporting Line Management](workforce-management/docs/usecases/uc-21-team-report-line-management/uc-21-team-report-line-management.png)

### Administration, Reporting, and Tenant

### 22. Workforce Dashboard
![Workforce Dashboard](workforce-management/docs/usecases/uc-22-workforce-dashboard/uc-22-workforce-dashboard.png)

### 23. Workforce Reporting and Export
![Workforce Reporting and Export](workforce-management/docs/usecases/uc-23-workforce-reporting-export/uc-23-workforce-reporting-export.png)

### 24. Tenant Management
![Tenant Management](workforce-management/docs/usecases/uc-24-tenant-management/uc-24-tenant-management.png)

### 25. Tenant Configuration
![Tenant Configuration](workforce-management/docs/usecases/uc-25-tenant-configuration/uc-25-tenant-configuration.png)

### 26. Employment Engagement
![Employment Engagement](workforce-management/docs/usecases/uc-26-employment-engagement/uc-26-employment-engagement.png)

### 27. Compensation Plan and Total Rewards
![Compensation Plan and Total Rewards](workforce-management/docs/usecases/uc-27-compensation-plan-totalward/uc-27-compensation-plan-totalward.png)

### 28. Productivity and Activity Monitoring
![Productivity and Activity Monitoring](workforce-management/docs/usecases/uc-28-productivity-activity-monitoring/uc-28-productivity-activity-monitoring.png)

### 29. Screenshot, App, and URL Tracking
![Screenshot, App, and URL Tracking](workforce-management/docs/usecases/uc-29-screenshot-app-url-tracking/uc-29-screenshot-app-url-tracking.png)


```mermaid
flowchart TD
    ROOT["WORKFORCE MANAGEMENT<br/>EXTERNAL PORTALS"]

    ROOT --> CLIENT["Client Portal"]
    ROOT --> CANDIDATE["Candidate Portal"]
    ROOT --> PUBLIC["Public Career Area"]
    ROOT --> INTEGRATIONS["Third-party Integrations"]

    CLIENT --> CLIENT_DASH["Client Dashboard<br/>CL"]
    CLIENT --> CLIENT_PROJECTS["Client Projects<br/>CL"]
    CLIENT --> PROJECT_DETAIL["Project Detail<br/>CL"]
    CLIENT --> TASK_STATUS["Task & Milestone Status<br/>CL"]
    CLIENT --> TIME_BUDGET["Time & Budget View<br/>CL"]
    CLIENT --> FILES["Project Files<br/>CL"]
    CLIENT --> CLIENT_REPORTS["Client Reports<br/>CL"]

    CANDIDATE --> CAND_PROFILE["Candidate Profile<br/>CD"]
    CANDIDATE --> APPLICATIONS["My Applications<br/>CD"]
    CANDIDATE --> APPLICATION_DETAIL["Application Detail<br/>CD"]
    CANDIDATE --> STATUS["Application Status<br/>CD"]
    CANDIDATE --> INTERVIEWS["Interview Schedule<br/>CD"]
    CANDIDATE --> OFFER["Offer Details<br/>CD"]
    CANDIDATE --> ONBOARDING["Onboarding Progress<br/>CD"]

    PUBLIC --> CAREERS["Career Page<br/>Public"]
    PUBLIC --> JOB_SEARCH["Search Jobs<br/>Public"]
    PUBLIC --> JOB_DETAIL["Job Detail<br/>Public"]
    PUBLIC --> APPLY["Apply for Job<br/>Public"]
    PUBLIC --> REGISTER["Candidate Registration<br/>Public"]

    INTEGRATIONS --> EMAIL["Email Integration<br/>SA · TA"]
    INTEGRATIONS --> STORAGE["Cloud Storage<br/>SA · TA"]
    INTEGRATIONS --> CALENDAR["Calendar Integration<br/>SA · TA"]
    INTEGRATIONS --> PAY_GATEWAY["Payroll / Payment Gateway<br/>SA · TA"]
    INTEGRATIONS --> SSO["SSO / SAML / OAuth<br/>SA · TA"]
    INTEGRATIONS --> WEBHOOK["Webhooks / API<br/>SA · TA"]
    INTEGRATIONS --> INTEGRATION_LOG["Integration Logs<br/>SA · TA"]

    classDef root fill:#cffafe,stroke:#0891b2,color:#164e63,stroke-width:2px;
    classDef group fill:#ecfeff,stroke:#06b6d4,color:#155e75,stroke-width:1.5px;
    classDef screen fill:#f8fafc,stroke:#94a3b8,color:#0f172a,stroke-width:1px;

    class ROOT root;
    class CLIENT,CANDIDATE,PUBLIC,INTEGRATIONS group;
    class CLIENT_DASH,CLIENT_PROJECTS,PROJECT_DETAIL,TASK_STATUS,TIME_BUDGET,FILES,CLIENT_REPORTS,CAND_PROFILE,APPLICATIONS,APPLICATION_DETAIL,STATUS,INTERVIEWS,OFFER,ONBOARDING,CAREERS,JOB_SEARCH,JOB_DETAIL,APPLY,REGISTER,EMAIL,STORAGE,CALENDAR,PAY_GATEWAY,SSO,WEBHOOK,INTEGRATION_LOG screen;

    linkStyle default stroke:#64748b,stroke-width:1.2px;
```

## III. Information Architecture
IA is designed on this link [Link to] (https://lucid.app/lucidchart/228fd30f-d248-4dac-848c-a8e1fbea7d2f/edit?viewport_loc=-2411%2C-8810%2C17587%2C11345%2C0_0&invitationId=inv_d97e91bf-91ca-4307-8d73-eb570ff48ea6)