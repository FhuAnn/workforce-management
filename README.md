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

## High-Priority Features to Implement First (29)

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
|  10 | Onboarding management                    | Critical | Create onsite job locations, assign employees and schedules, and verify attendance using GPS or geofencing. |
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
|  26 | Employee Experience and Engagement       | High     | Publish company announcements, collect employee feedback, run satisfaction surveys, and monitor employee wellbeing and engagement.          |
|  27 | Compensation Planning and Total Rewards  | High     | Plan salary adjustments, benchmark compensation, manage compensation cycles, budgets, approvals, and employee total rewards statements.     |
|  28 | Productivity and Activity Monitoring     | High     | Track activity levels, active and idle time, workload patterns, utilization, and productivity trends during recorded work sessions.         |
|  29 | Screenshot, App, and URL Tracking        | High     | Capture optional work screenshots and record applications and websites used while employees track time, with configurable privacy controls. |


## II. Use Case Images

### Core Time, Attendance, and Leave

### 1. Project and Time Tracking
![alt text](workforce-management/docs/imgs/uc01.png)
### 2. Payroll Processing
![alt text](workforce-management/docs/imgs/uc02.png)

### 3. Payslip Management
![alt text](workforce-management/docs/imgs/uc03.png)

### 4. Clock In / Clock Out
![alt text](workforce-management/docs/imgs/uc04.png)

### 5. Break Tracking
![alt text](workforce-management/docs/imgs/uc05.png)

### 6. Attendance Record Management
![alt text](workforce-management/docs/imgs/uc06.png)

### 7. Overtime Management
![alt text](workforce-management/docs/imgs/uc07.png)

### 8. Timesheet Management
![alt text](workforce-management/docs/imgs/uc08.png)

### 9. Time Review and Approval
![alt text](workforce-management/docs/imgs/uc09.png)

### 10. Onsite Work Location Management
![Onsite Work Location Management](workforce-management/docs/usecases/uc10-onsite-work-location-management/uc10-onsite-work-location-management.png)

### 11. Employment Lifecycle Management
![alt text](workforce-management/docs/imgs/uc11.png)

### 12. Leave Request Management
![alt text](workforce-management/docs/imgs/uc12.png)

### 13. Leave Balance Management
![alt text](workforce-management/docs/imgs/uc13.png)

### 14. Leave Approval
![alt text](workforce-management/docs/imgs/uc14.png)

### Project, Task, and Productivity

### 15. Project Management
![alt text](workforce-management/docs/imgs/uc15.png)

### 16. Project Member Management
![alt text](workforce-management/docs/imgs/uc16.png)

### 17. Task Management
![alt text](workforce-management/docs/imgs/uc17.png)

### 18. Task Progress Management
![alt text](workforce-management/docs/imgs/uc18.png)

### 19. Department Management
![alt text](workforce-management/docs/imgs/uc19.png)

### 20. Position Management
![alt text](workforce-management/docs/imgs/uc20.png)

### 21. Team and Reporting Line Management
![alt text](workforce-management/docs/imgs/uc21.png)

### 22. Workforce Dashboard
![alt text](workforce-management/docs/imgs/uc22.png)
### 23. Workforce Reporting and Export
![alt text](workforce-management/docs/imgs/uc23.png)

### 24. Tenant Management
![alt text](workforce-management/docs/imgs/uc24.png)

### 25. Tenant Configuration
![alt text](workforce-management/docs/imgs/uc25.png)

### 26. Employment Engagement
![alt text](workforce-management/docs/imgs/uc26.png)

### 27. Compensation Plan and Total Rewards
![alt text](workforce-management/docs/imgs/uc27.png)

### 28. Productivity and Activity Monitoring
![alt text](workforce-management/docs/imgs/uc28.png)

### 29. Screenshot, App, and URL Tracking
![alt text](workforce-management/docs/imgs/uc29.png)



## III. Swimlane Images

### Core Time, Attendance, and Leave

#### 1. Project and Task Time Tracking
![Project and Task Time Tracking](workforce-management/docs/swimlanes/imgs/01_project_task_time_tracking.png)

#### 2A. Payroll Processing - Prepare Payroll
![Payroll Processing - Prepare Payroll](workforce-management/docs/swimlanes/imgs/02a_payroll_processing_prepare.png)

#### 2B. Payroll Processing - Approval and Payment
![Payroll Processing - Approval and Payment](workforce-management/docs/swimlanes/imgs/02b_payroll_processing_approval.png)

#### 4. Clock In / Clock Out
![Clock In / Clock Out](workforce-management/docs/swimlanes/imgs/04_clock_in_clock_out.png)

#### 5. Break Tracking
![Break Tracking](workforce-management/docs/swimlanes/imgs/05_break_tracking.png)

#### 6. Attendance Record Management
![Attendance Record Management](workforce-management/docs/swimlanes/imgs/06_attendance_record_management.png)

#### 7A. Overtime Management - Request and Approval
![Overtime Management - Request and Approval](workforce-management/docs/swimlanes/imgs/07a_overtime_request_approval.png)

#### 7B. Overtime Management - Validation and Pay
![Overtime Management - Validation and Pay](workforce-management/docs/swimlanes/imgs/07b_overtime_record_pay.png)

#### 8. Timesheet Management
![Timesheet Management](workforce-management/docs/swimlanes/imgs/08_timesheet_management.png)

#### 9. Timesheet Review and Approval
![Timesheet Review and Approval](workforce-management/docs/swimlanes/imgs/09_timesheet_review_approval.png)

#### 10A. Onboarding Management - Prepare New Hire
![Onboarding Management - Prepare New Hire](workforce-management/docs/swimlanes/imgs/10a_onboarding_plan.png)

#### 10B. Onboarding Management - Complete Onboarding
![Onboarding Management - Complete Onboarding](workforce-management/docs/swimlanes/imgs/10b_onboarding_execution.png)

#### 11. Employment Lifecycle Management
![Employment Lifecycle Management](workforce-management/docs/swimlanes/imgs/11_employment_lifecycle_management.png)

#### 12. Leave Request Management
![Leave Request Management](workforce-management/docs/swimlanes/imgs/12_leave_request_management.png)

#### 13. Leave Balance Management
![Leave Balance Management](workforce-management/docs/swimlanes/imgs/13_leave_balance_management.png)

#### 14. Leave Approval
![Leave Approval](workforce-management/docs/swimlanes/imgs/14_leave_approval.png)

### Project, Task, and Organizational Management

#### 15. Project Management
![Project Management](workforce-management/docs/swimlanes/imgs/15_project_management.png)

#### 16. Project Member Management
![Project Member Management](workforce-management/docs/swimlanes/imgs/16_project_member_management.png)

#### 17. Task Management
![Task Management](workforce-management/docs/swimlanes/imgs/17_task_management.png)

#### 18. Task Progress Management
![Task Progress Management](workforce-management/docs/swimlanes/imgs/18_task_progress_management.png)

#### 19. Department Management
![Department Management](workforce-management/docs/swimlanes/imgs/19_department_management.png)

#### 20. Position Management
![Position Management](workforce-management/docs/swimlanes/imgs/20_position_management.png)

#### 21. Team and Reporting Line Management
![Team and Reporting Line Management](workforce-management/docs/swimlanes/imgs/21_team_reporting_line_management.png)

### Administration, Reporting, Tenant, and Engagement

#### 22. Workforce Dashboard
![Workforce Dashboard](workforce-management/docs/swimlanes/imgs/22_workforce_dashboard.png)

#### 23. Workforce Reporting and Export
![Workforce Reporting and Export](workforce-management/docs/swimlanes/imgs/23_workforce_reporting_export.png)

#### 24A. Tenant Management - Create Organization
![Tenant Management - Create Organization](workforce-management/docs/swimlanes/imgs/24a_tenant_management_create.png)

#### 24B. Tenant Management - Data Isolation
![Tenant Management - Data Isolation](workforce-management/docs/swimlanes/imgs/24b_tenant_management_isolation.png)

#### 26A. Employee Experience - Announcements
![Employee Experience - Announcements](workforce-management/docs/swimlanes/imgs/26a_employee_engagement_announcement.png)

#### 26B. Employee Engagement - Survey and Feedback
![Employee Engagement - Survey and Feedback](workforce-management/docs/swimlanes/imgs/26b_employee_engagement_survey.png)

#### 27A. Compensation Planning - Review Cycle
![Compensation Planning - Review Cycle](workforce-management/docs/swimlanes/imgs/27a_compensation_planning_cycle.png)

#### 27B. Compensation Planning - Approval and Total Rewards
![Compensation Planning - Approval and Total Rewards](workforce-management/docs/swimlanes/imgs/27b_compensation_approval_rewards.png)

#### 28A. Productivity Monitoring - Collect Activity
![Productivity Monitoring - Collect Activity](workforce-management/docs/swimlanes/imgs/28a_productivity_activity_collection.png)

#### 28B. Productivity Monitoring - Manager Review
![Productivity Monitoring - Manager Review](workforce-management/docs/swimlanes/imgs/28b_productivity_activity_review.png)

#### 29A. Screenshot Tracking - Capture and Privacy
![Screenshot Tracking - Capture and Privacy](workforce-management/docs/swimlanes/imgs/29a_screenshot_capture_privacy.png)

#### 29B. App and URL Tracking
![App and URL Tracking](workforce-management/docs/swimlanes/imgs/29b_app_url_tracking.png)

#### 29C. Screenshot Review and Deletion
![Screenshot Review and Deletion](workforce-management/docs/swimlanes/imgs/29c_screenshot_review_delete.png)


## IV. Information Architecture and UI Hierachy
IA is designed on this link [Link to] (https://lucid.app/lucidchart/228fd30f-d248-4dac-848c-a8e1fbea7d2f/edit?viewport_loc=-2411%2C-8810%2C17587%2C11345%2C0_0&invitationId=inv_d97e91bf-91ca-4307-8d73-eb570ff48ea6)


# 1. Overall Information Architecture

```mermaid
flowchart TD
    ROOT["Workforce Management SaaS"]

    ROOT --> PUBLIC["Public & Authentication"]
    ROOT --> APP["Core Application"]
    ROOT --> ADMIN["Administration"]

    PUBLIC --> LANDING["Landing Page"]
    PUBLIC --> LOGIN["Login"]
    PUBLIC --> FORGOT["Forgot Password"]
    PUBLIC --> RESET["Reset Password"]
    PUBLIC --> VERIFY["Account Verification"]
    PUBLIC --> INVITE["Accept Invitation"]

    APP --> DASHBOARD["Dashboard"]
    APP --> PEOPLE["People & Employee Management"]
    APP --> TIME["Time Tracking"]
    APP --> ATTENDANCE["Attendance & Leave"]
    APP --> PROJECT["Projects & Tasks"]
    APP --> PAYROLL["Payroll & Payslips"]
    APP --> ACTIVITY["Activity Monitoring"]
    APP --> REPORTS["Reports & Analytics"]
    APP --> NOTIFICATIONS["Notifications"]

    ADMIN --> TENANT["Tenant Administration"]
    ADMIN --> USERS["Users, Roles & Permissions"]
    ADMIN --> POLICIES["Policies & Configuration"]
    ADMIN --> INTEGRATIONS["Integrations"]
    ADMIN --> AUDIT["Audit Logs"]
    ADMIN --> SYSTEM["System Administration"]

    classDef root fill:#000000,stroke:#2563eb,color:#ffffff
    classDef group fill:#ede9fe,stroke:#7c3aed,color:#000000
    classDef module fill:#f8fafc,stroke:#94a3b8,color:#000000

    class ROOT root
    class PUBLIC,APP,ADMIN group
    class LANDING,LOGIN,FORGOT,RESET,VERIFY,INVITE,DASHBOARD,PEOPLE,TIME,ATTENDANCE,PROJECT,PAYROLL,ACTIVITY,REPORTS,NOTIFICATIONS,TENANT,USERS,POLICIES,INTEGRATIONS,AUDIT,SYSTEM module
```

---

# 2. Public & Authentication

## 2.1 Information Architecture

```mermaid
flowchart TD
    AUTH["Public & Authentication"]

    AUTH --> PUBLIC["Public Pages"]
    AUTH --> ACCESS["Account Access"]
    AUTH --> RECOVERY["Account Recovery"]
    AUTH --> ONBOARDING["User Onboarding"]

    PUBLIC --> LANDING["Landing Page"]
    PUBLIC --> PRICING["Pricing"]
    PUBLIC --> CONTACT["Contact"]
    PUBLIC --> PRIVACY["Privacy Policy"]
    PUBLIC --> TERMS["Terms of Service"]

    ACCESS --> LOGIN["Login"]
    ACCESS --> SSO["Single Sign-On"]
    ACCESS --> MFA["Multi-Factor Authentication"]

    RECOVERY --> FORGOT["Forgot Password"]
    RECOVERY --> RESET["Reset Password"]

    ONBOARDING --> VERIFY["Verify Account"]
    ONBOARDING --> INVITATION["Accept Invitation"]
    ONBOARDING --> CREATE_PASSWORD["Create Password"]
    ONBOARDING --> PROFILE_SETUP["Initial Profile Setup"]

    classDef root fill:#000000,stroke:#2563eb,color:#ffffff
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class AUTH root
    class PUBLIC,ACCESS,RECOVERY,ONBOARDING category
    class LANDING,PRICING,CONTACT,PRIVACY,TERMS,LOGIN,SSO,MFA,FORGOT,RESET,VERIFY,INVITATION,CREATE_PASSWORD,PROFILE_SETUP page
```

## 2.2 UI Hierarchy — Login Page

```mermaid
flowchart TD
    PAGE["Login Page"]

    PAGE --> BRAND["Brand Area"]
    PAGE --> FORM["Login Form"]
    PAGE --> ALTERNATIVE["Alternative Login"]
    PAGE --> SUPPORT["Support Links"]

    BRAND --> LOGO["Product Logo"]
    BRAND --> TITLE["Welcome Message"]
    BRAND --> DESCRIPTION["Product Description"]

    FORM --> EMAIL["Email Input"]
    FORM --> PASSWORD["Password Input"]
    FORM --> REMEMBER["Remember Me"]
    FORM --> SUBMIT["Login Button"]
    FORM --> ERROR["Validation/Error Message"]

    ALTERNATIVE --> GOOGLE["Continue with Google"]
    ALTERNATIVE --> MICROSOFT["Continue with Microsoft"]
    ALTERNATIVE --> SSO["Company SSO"]

    SUPPORT --> FORGOT["Forgot Password Link"]
    SUPPORT --> CONTACT["Contact Administrator"]
    SUPPORT --> TERMS["Terms & Privacy"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class BRAND,FORM,ALTERNATIVE,SUPPORT section
    class LOGO,TITLE,DESCRIPTION,EMAIL,PASSWORD,REMEMBER,SUBMIT,ERROR,GOOGLE,MICROSOFT,SSO,FORGOT,CONTACT,TERMS component
```

---

# 3. Dashboard

## 3.1 Information Architecture

```mermaid
flowchart TD
    DASH["Dashboard"]

    DASH --> PERSONAL["Personal Dashboard"]
    DASH --> MANAGER["Manager Dashboard"]
    DASH --> HR["HR Dashboard"]
    DASH --> PAYROLL["Payroll Dashboard"]
    DASH --> ADMIN["Administration Dashboard"]

    PERSONAL --> MY_TIME["My Working Time"]
    PERSONAL --> MY_TASKS["My Tasks"]
    PERSONAL --> MY_LEAVE["My Leave Balance"]
    PERSONAL --> MY_PAYSLIPS["My Payslips"]
    PERSONAL --> MY_NOTIFICATIONS["My Notifications"]

    MANAGER --> TEAM_STATUS["Team Status"]
    MANAGER --> APPROVALS["Pending Approvals"]
    MANAGER --> TEAM_TIME["Team Time Summary"]
    MANAGER --> WORKLOAD["Team Workload"]

    HR --> HEADCOUNT["Headcount"]
    HR --> ATTENDANCE["Attendance Summary"]
    HR --> ONBOARDING["Onboarding Progress"]
    HR --> LEAVE_SUMMARY["Leave Summary"]

    PAYROLL --> PAYROLL_STATUS["Payroll Status"]
    PAYROLL --> PAYROLL_ALERTS["Payroll Alerts"]
    PAYROLL --> PAYROLL_COST["Payroll Cost"]

    ADMIN --> TENANT_USAGE["Tenant Usage"]
    ADMIN --> ACTIVE_USERS["Active Users"]
    ADMIN --> SYSTEM_ALERTS["System Alerts"]

    classDef root fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class DASH root
    class PERSONAL,MANAGER,HR,PAYROLL,ADMIN category
    class MY_TIME,MY_TASKS,MY_LEAVE,MY_PAYSLIPS,MY_NOTIFICATIONS,TEAM_STATUS,APPROVALS,TEAM_TIME,WORKLOAD,HEADCOUNT,ATTENDANCE,ONBOARDING,LEAVE_SUMMARY,PAYROLL_STATUS,PAYROLL_ALERTS,PAYROLL_COST,TENANT_USAGE,ACTIVE_USERS,SYSTEM_ALERTS page
```

## 3.2 UI Hierarchy — Dashboard Page

```mermaid
flowchart TD
    PAGE["Dashboard Page"]

    PAGE --> GLOBAL["Global App Shell"]
    PAGE --> HEADER["Dashboard Header"]
    PAGE --> KPI["Summary Cards"]
    PAGE --> MAIN["Main Dashboard Content"]
    PAGE --> SIDEBAR["Secondary Panel"]

    GLOBAL --> NAV["Main Sidebar"]
    GLOBAL --> TOPBAR["Top Navigation"]
    GLOBAL --> TENANT["Tenant Switcher"]
    GLOBAL --> PROFILE["User Profile Menu"]

    HEADER --> TITLE["Page Title"]
    HEADER --> DATE["Date Range"]
    HEADER --> FILTER["Dashboard Filters"]
    HEADER --> CUSTOMIZE["Customize Dashboard"]

    KPI --> HOURS["Hours Worked"]
    KPI --> PRESENT["Employees Present"]
    KPI --> PENDING["Pending Approvals"]
    KPI --> PAYROLL["Payroll Status"]

    MAIN --> CHART["Time & Attendance Chart"]
    MAIN --> ACTIVITY["Recent Activity"]
    MAIN --> TASKS["Tasks and Deadlines"]
    MAIN --> APPROVALS["Approval Queue"]

    SIDEBAR --> CLOCK["Clock In / Out Widget"]
    SIDEBAR --> LEAVE["Leave Balance"]
    SIDEBAR --> ANNOUNCEMENT["Announcements"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class GLOBAL,HEADER,KPI,MAIN,SIDEBAR section
    class NAV,TOPBAR,TENANT,PROFILE,TITLE,DATE,FILTER,CUSTOMIZE,HOURS,PRESENT,PENDING,PAYROLL,CHART,ACTIVITY,TASKS,APPROVALS,CLOCK,LEAVE,ANNOUNCEMENT component
```

---

# 4. People & Employee Management

## 4.1 Information Architecture

```mermaid
flowchart TD
    PEOPLE["People & Employee Management"]

    PEOPLE --> DIRECTORY["Employee Directory"]
    PEOPLE --> PROFILE["Employee Profile"]
    PEOPLE --> EMPLOYMENT["Employment Information"]
    PEOPLE --> DOCUMENTS["Employee Documents"]
    PEOPLE --> ONBOARDING["Onboarding"]
    PEOPLE --> OFFBOARDING["Offboarding"]
    PEOPLE --> ORG["Organization Structure"]

    DIRECTORY --> EMPLOYEE_LIST["Employee List"]
    DIRECTORY --> EMPLOYEE_SEARCH["Search & Filters"]
    DIRECTORY --> IMPORT["Import Employees"]
    DIRECTORY --> EXPORT["Export Employees"]

    PROFILE --> PERSONAL["Personal Information"]
    PROFILE --> CONTACT["Contact Information"]
    PROFILE --> EMERGENCY["Emergency Contact"]
    PROFILE --> JOB["Job Information"]
    PROFILE --> COMPENSATION["Compensation"]
    PROFILE --> BANK["Bank Information"]

    EMPLOYMENT --> CONTRACT["Employment Contract"]
    EMPLOYMENT --> STATUS["Employment Status"]
    EMPLOYMENT --> HISTORY["Employment History"]

    DOCUMENTS --> DOCUMENT_LIST["Document List"]
    DOCUMENTS --> UPLOAD["Upload Document"]
    DOCUMENTS --> CATEGORIES["Document Categories"]

    ONBOARDING --> TEMPLATE["Onboarding Templates"]
    ONBOARDING --> CHECKLIST["Onboarding Checklist"]
    ONBOARDING --> ASSIGN_TASKS["Assign Tasks"]
    ONBOARDING --> PROGRESS["Onboarding Progress"]

    OFFBOARDING --> OFFBOARD_CHECKLIST["Offboarding Checklist"]
    OFFBOARDING --> ACCESS_REVOKE["Access Revocation"]
    OFFBOARDING --> EXIT["Exit Information"]

    ORG --> DEPARTMENTS["Departments"]
    ORG --> TEAMS["Teams"]
    ORG --> POSITIONS["Positions"]
    ORG --> ORG_CHART["Organization Chart"]

    classDef root fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PEOPLE root
    class DIRECTORY,PROFILE,EMPLOYMENT,DOCUMENTS,ONBOARDING,OFFBOARDING,ORG category
    class EMPLOYEE_LIST,EMPLOYEE_SEARCH,IMPORT,EXPORT,PERSONAL,CONTACT,EMERGENCY,JOB,COMPENSATION,BANK,CONTRACT,STATUS,HISTORY,DOCUMENT_LIST,UPLOAD,CATEGORIES,TEMPLATE,CHECKLIST,ASSIGN_TASKS,PROGRESS,OFFBOARD_CHECKLIST,ACCESS_REVOKE,EXIT,DEPARTMENTS,TEAMS,POSITIONS,ORG_CHART page
```

## 4.2 UI Hierarchy — Employee Directory

```mermaid
flowchart TD
    PAGE["Employee Directory Page"]

    PAGE --> SHELL["Application Shell"]
    PAGE --> HEADER["Page Header"]
    PAGE --> TOOLBAR["Directory Toolbar"]
    PAGE --> CONTENT["Employee Content"]
    PAGE --> PAGINATION["Pagination"]

    SHELL --> SIDEBAR["Main Sidebar"]
    SHELL --> TOPBAR["Top Navigation"]
    SHELL --> BREADCRUMB["People / Employees"]

    HEADER --> TITLE["Employees"]
    HEADER --> COUNT["Employee Count"]
    HEADER --> ADD["Add Employee"]
    HEADER --> IMPORT["Import"]
    HEADER --> EXPORT["Export"]

    TOOLBAR --> SEARCH["Search Employees"]
    TOOLBAR --> DEPARTMENT["Department Filter"]
    TOOLBAR --> STATUS["Status Filter"]
    TOOLBAR --> LOCATION["Location Filter"]
    TOOLBAR --> VIEW["Table/Grid Toggle"]

    CONTENT --> TABLE["Employee Table"]
    CONTENT --> EMPTY["Empty State"]
    CONTENT --> BULK["Bulk Action Bar"]

    TABLE --> AVATAR["Avatar"]
    TABLE --> NAME["Name"]
    TABLE --> JOB["Job Title"]
    TABLE --> DEPT["Department"]
    TABLE --> MANAGER["Manager"]
    TABLE --> EMP_STATUS["Status"]
    TABLE --> ACTIONS["Row Actions"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class SHELL,HEADER,TOOLBAR,CONTENT,PAGINATION section
    class SIDEBAR,TOPBAR,BREADCRUMB,TITLE,COUNT,ADD,IMPORT,EXPORT,SEARCH,DEPARTMENT,STATUS,LOCATION,VIEW,TABLE,EMPTY,BULK,AVATAR,NAME,JOB,DEPT,MANAGER,EMP_STATUS,ACTIONS component
```

## 4.3 UI Hierarchy — Employee Detail

```mermaid
flowchart TD
    PAGE["Employee Detail Page"]

    PAGE --> NAV["Application Navigation"]
    PAGE --> PROFILE_HEADER["Employee Profile Header"]
    PAGE --> TABS["Profile Tabs"]
    PAGE --> CONTENT["Tab Content"]
    PAGE --> ACTION_PANEL["Employee Actions"]

    PROFILE_HEADER --> AVATAR["Profile Photo"]
    PROFILE_HEADER --> NAME["Employee Name"]
    PROFILE_HEADER --> TITLE["Job Title"]
    PROFILE_HEADER --> STATUS["Employment Status"]
    PROFILE_HEADER --> CONTACT["Quick Contact"]
    PROFILE_HEADER --> EDIT["Edit Profile"]

    TABS --> OVERVIEW["Overview"]
    TABS --> JOB["Job"]
    TABS --> TIME["Time & Attendance"]
    TABS --> LEAVE["Leave"]
    TABS --> PAYROLL["Payroll"]
    TABS --> DOCUMENTS["Documents"]
    TABS --> HISTORY["History"]

    CONTENT --> SUMMARY["Employee Summary"]
    CONTENT --> INFO_CARDS["Information Cards"]
    CONTENT --> TIMELINE["Activity Timeline"]

    ACTION_PANEL --> CHANGE_STATUS["Change Status"]
    ACTION_PANEL --> RESET_PASSWORD["Reset Password"]
    ACTION_PANEL --> OFFBOARD["Start Offboarding"]
    ACTION_PANEL --> ARCHIVE["Archive Employee"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class NAV,PROFILE_HEADER,TABS,CONTENT,ACTION_PANEL section
    class AVATAR,NAME,TITLE,STATUS,CONTACT,EDIT,OVERVIEW,JOB,TIME,LEAVE,PAYROLL,DOCUMENTS,HISTORY,SUMMARY,INFO_CARDS,TIMELINE,CHANGE_STATUS,RESET_PASSWORD,OFFBOARD,ARCHIVE component
```

---

# 5. Time Tracking

## 5.1 Information Architecture

```mermaid
flowchart TD
    TIME["Time Tracking"]

    TIME --> TIMER["Timer"]
    TIME --> TIMESHEETS["Timesheets"]
    TIME --> MANUAL["Manual Time"]
    TIME --> BREAKS["Break Tracking"]
    TIME --> APPROVALS["Timesheet Approvals"]
    TIME --> SETTINGS["Time Tracking Settings"]

    TIMER --> CLOCK["Clock In / Clock Out"]
    TIMER --> RUNNING["Running Timer"]
    TIMER --> PROJECT_SELECT["Select Project"]
    TIMER --> TASK_SELECT["Select Task"]
    TIMER --> NOTES["Work Notes"]

    TIMESHEETS --> DAILY["Daily Timesheet"]
    TIMESHEETS --> WEEKLY["Weekly Timesheet"]
    TIMESHEETS --> MONTHLY["Monthly Summary"]
    TIMESHEETS --> PROJECT_TIME["Time by Project"]
    TIMESHEETS --> TASK_TIME["Time by Task"]

    MANUAL --> ADD_TIME["Add Manual Entry"]
    MANUAL --> EDIT_TIME["Edit Time Entry"]
    MANUAL --> DELETE_TIME["Delete Time Entry"]

    BREAKS --> START_BREAK["Start Break"]
    BREAKS --> END_BREAK["End Break"]
    BREAKS --> BREAK_HISTORY["Break History"]

    APPROVALS --> SUBMIT["Submit Timesheet"]
    APPROVALS --> REVIEW["Review Timesheet"]
    APPROVALS --> APPROVE["Approve Timesheet"]
    APPROVALS --> REJECT["Reject Timesheet"]
    APPROVALS --> CORRECTION["Request Correction"]

    SETTINGS --> RULES["Time Rules"]
    SETTINGS --> ROUNDING["Time Rounding"]
    SETTINGS --> MANUAL_POLICY["Manual Time Policy"]
    SETTINGS --> APPROVAL_POLICY["Approval Workflow"]

    classDef root fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef critical fill:#fee2e2,stroke:#dc2626, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class TIME root
    class TIMER,TIMESHEETS,MANUAL,BREAKS,APPROVALS,SETTINGS category
    class CLOCK,RUNNING,DAILY,WEEKLY,SUBMIT,REVIEW,APPROVE,REJECT critical
    class PROJECT_SELECT,TASK_SELECT,NOTES,MONTHLY,PROJECT_TIME,TASK_TIME,ADD_TIME,EDIT_TIME,DELETE_TIME,START_BREAK,END_BREAK,BREAK_HISTORY,CORRECTION,RULES,ROUNDING,MANUAL_POLICY,APPROVAL_POLICY page
```

## 5.2 UI Hierarchy — Time Tracking Overview

```mermaid
flowchart TD
    PAGE["Time Tracking Overview"]

    PAGE --> HEADER["Page Header"]
    PAGE --> TIMER["Timer Card"]
    PAGE --> SUMMARY["Time Summary"]
    PAGE --> TIMESHEET["Weekly Timesheet"]
    PAGE --> ACTIVITY["Recent Time Entries"]

    HEADER --> TITLE["Time Tracking"]
    HEADER --> DATE["Date Selector"]
    HEADER --> ADD["Add Manual Time"]
    HEADER --> SUBMIT["Submit Timesheet"]

    TIMER --> STATUS["Timer Status"]
    TIMER --> DURATION["Running Duration"]
    TIMER --> PROJECT["Project Selector"]
    TIMER --> TASK["Task Selector"]
    TIMER --> NOTE["Work Note"]
    TIMER --> START_STOP["Start / Stop Button"]
    TIMER --> BREAK["Start Break"]

    SUMMARY --> TODAY["Today"]
    SUMMARY --> WEEK["This Week"]
    SUMMARY --> BILLABLE["Billable Hours"]
    SUMMARY --> OVERTIME["Overtime"]

    TIMESHEET --> DAY_COLUMNS["Day Columns"]
    TIMESHEET --> PROJECT_ROWS["Project Rows"]
    TIMESHEET --> TOTALS["Daily and Weekly Totals"]
    TIMESHEET --> STATUS_BADGE["Submission Status"]

    ACTIVITY --> ENTRY_LIST["Time Entry List"]
    ACTIVITY --> EDIT["Edit Entry"]
    ACTIVITY --> DELETE["Delete Entry"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class HEADER,TIMER,SUMMARY,TIMESHEET,ACTIVITY section
    class TITLE,DATE,ADD,SUBMIT,STATUS,DURATION,PROJECT,TASK,NOTE,START_STOP,BREAK,TODAY,WEEK,BILLABLE,OVERTIME,DAY_COLUMNS,PROJECT_ROWS,TOTALS,STATUS_BADGE,ENTRY_LIST,EDIT,DELETE component
```

---

# 6. Attendance, Leave & Overtime

## 6.1 Information Architecture

```mermaid
flowchart TD
    ATT["Attendance, Leave & Overtime"]

    ATT --> ATTENDANCE["Attendance"]
    ATT --> LEAVE["Leave Management"]
    ATT --> OVERTIME["Overtime"]
    ATT --> SCHEDULE["Work Schedules"]
    ATT --> HOLIDAY["Holiday Calendar"]

    ATTENDANCE --> RECORDS["Attendance Records"]
    ATTENDANCE --> DAILY["Daily Attendance"]
    ATTENDANCE --> TEAM["Team Attendance"]
    ATTENDANCE --> CORRECTION["Attendance Correction"]
    ATTENDANCE --> ABSENCE["Absence Management"]

    LEAVE --> REQUEST["Request Leave"]
    LEAVE --> BALANCE["Leave Balance"]
    LEAVE --> HISTORY["Leave History"]
    LEAVE --> APPROVAL["Leave Approval"]
    LEAVE --> TYPES["Leave Types"]
    LEAVE --> POLICIES["Leave Policies"]

    OVERTIME --> OT_REQUEST["Request Overtime"]
    OVERTIME --> OT_RECORD["Record Overtime"]
    OVERTIME --> OT_APPROVAL["Overtime Approval"]
    OVERTIME --> OT_HISTORY["Overtime History"]
    OVERTIME --> OT_RULES["Overtime Rules"]

    SCHEDULE --> MY_SCHEDULE["My Schedule"]
    SCHEDULE --> TEAM_SCHEDULE["Team Schedule"]
    SCHEDULE --> SHIFT["Shift Management"]
    SCHEDULE --> ASSIGN["Schedule Assignment"]

    HOLIDAY --> HOLIDAY_LIST["Holiday List"]
    HOLIDAY --> HOLIDAY_GROUPS["Holiday Groups"]
    HOLIDAY --> HOLIDAY_SETTINGS["Holiday Settings"]

    classDef root fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef critical fill:#fee2e2,stroke:#dc2626, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class ATT root
    class ATTENDANCE,LEAVE,OVERTIME,SCHEDULE,HOLIDAY category
    class RECORDS,REQUEST,APPROVAL,OT_REQUEST,OT_APPROVAL critical
    class DAILY,TEAM,CORRECTION,ABSENCE,BALANCE,HISTORY,TYPES,POLICIES,OT_RECORD,OT_HISTORY,OT_RULES,MY_SCHEDULE,TEAM_SCHEDULE,SHIFT,ASSIGN,HOLIDAY_LIST,HOLIDAY_GROUPS,HOLIDAY_SETTINGS page
```

## 6.2 UI Hierarchy — Leave Request

```mermaid
flowchart TD
    PAGE["Leave Request Page"]

    PAGE --> HEADER["Page Header"]
    PAGE --> BALANCE["Leave Balance Summary"]
    PAGE --> FORM["Request Form"]
    PAGE --> CALENDAR["Leave Calendar"]
    PAGE --> POLICY["Policy Information"]

    HEADER --> TITLE["Request Leave"]
    HEADER --> HISTORY["View Leave History"]

    BALANCE --> ANNUAL["Annual Leave"]
    BALANCE --> SICK["Sick Leave"]
    BALANCE --> OTHER["Other Leave"]

    FORM --> TYPE["Leave Type"]
    FORM --> DATE_RANGE["Start and End Date"]
    FORM --> PARTIAL["Full Day / Half Day"]
    FORM --> DURATION["Calculated Duration"]
    FORM --> REASON["Reason"]
    FORM --> ATTACHMENT["Attachment"]
    FORM --> APPROVER["Approver"]
    FORM --> SUBMIT["Submit Request"]

    CALENDAR --> TEAM_LEAVE["Team Leave Events"]
    CALENDAR --> HOLIDAYS["Public Holidays"]

    POLICY --> NOTICE["Notice Requirement"]
    POLICY --> BALANCE_RULE["Balance Rule"]
    POLICY --> APPROVAL_RULE["Approval Process"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class HEADER,BALANCE,FORM,CALENDAR,POLICY section
    class TITLE,HISTORY,ANNUAL,SICK,OTHER,TYPE,DATE_RANGE,PARTIAL,DURATION,REASON,ATTACHMENT,APPROVER,SUBMIT,TEAM_LEAVE,HOLIDAYS,NOTICE,BALANCE_RULE,APPROVAL_RULE component
```

---

# 7. Projects & Tasks

## 7.1 Information Architecture

```mermaid
flowchart TD
    PROJECT["Projects & Tasks"]

    PROJECT --> PROJECTS["Project Management"]
    PROJECT --> MEMBERS["Project Members"]
    PROJECT --> TASKS["Task Management"]
    PROJECT --> CLIENTS["Client Management"]
    PROJECT --> BILLING["Project Billing"]

    PROJECTS --> PROJECT_LIST["Project List"]
    PROJECTS --> CREATE_PROJECT["Create Project"]
    PROJECTS --> PROJECT_DETAIL["Project Detail"]
    PROJECTS --> ARCHIVE_PROJECT["Archive Project"]

    MEMBERS --> ASSIGN_MEMBER["Assign Member"]
    MEMBERS --> REMOVE_MEMBER["Remove Member"]
    MEMBERS --> RESPONSIBILITY["Project Responsibility"]
    MEMBERS --> MEMBER_RATE["Member Billing Rate"]

    TASKS --> TASK_LIST["Task List"]
    TASKS --> CREATE_TASK["Create Task"]
    TASKS --> TASK_DETAIL["Task Detail"]
    TASKS --> ASSIGN_TASK["Assign Task"]
    TASKS --> TASK_STATUS["Task Status"]
    TASKS --> TASK_DEADLINE["Task Deadline"]

    CLIENTS --> CLIENT_LIST["Client List"]
    CLIENTS --> CLIENT_DETAIL["Client Detail"]
    CLIENTS --> CLIENT_PROJECTS["Client Projects"]

    BILLING --> BILLABLE_STATUS["Billable / Non-Billable"]
    BILLING --> BILLING_RATE["Billing Rate"]
    BILLING --> PROJECT_BUDGET["Project Budget"]
    BILLING --> COST_SUMMARY["Cost Summary"]

    classDef root fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PROJECT root
    class PROJECTS,MEMBERS,TASKS,CLIENTS,BILLING category
    class PROJECT_LIST,CREATE_PROJECT,PROJECT_DETAIL,ARCHIVE_PROJECT,ASSIGN_MEMBER,REMOVE_MEMBER,RESPONSIBILITY,MEMBER_RATE,TASK_LIST,CREATE_TASK,TASK_DETAIL,ASSIGN_TASK,TASK_STATUS,TASK_DEADLINE,CLIENT_LIST,CLIENT_DETAIL,CLIENT_PROJECTS,BILLABLE_STATUS,BILLING_RATE,PROJECT_BUDGET,COST_SUMMARY page
```

## 7.2 UI Hierarchy — Project Detail

```mermaid
flowchart TD
    PAGE["Project Detail Page"]

    PAGE --> HEADER["Project Header"]
    PAGE --> SUMMARY["Project Summary"]
    PAGE --> TABS["Project Tabs"]
    PAGE --> CONTENT["Selected Tab Content"]
    PAGE --> ACTIONS["Project Actions"]

    HEADER --> NAME["Project Name"]
    HEADER --> CLIENT["Client"]
    HEADER --> STATUS["Project Status"]
    HEADER --> MANAGER["Project Manager"]
    HEADER --> EDIT["Edit Project"]

    SUMMARY --> HOURS["Tracked Hours"]
    SUMMARY --> BUDGET["Budget Usage"]
    SUMMARY --> MEMBERS["Team Members"]
    SUMMARY --> TASK_PROGRESS["Task Progress"]

    TABS --> OVERVIEW["Overview"]
    TABS --> TASKS["Tasks"]
    TABS --> MEMBERS_TAB["Members"]
    TABS --> TIME["Time Entries"]
    TABS --> ACTIVITY["Activity"]
    TABS --> SETTINGS["Settings"]

    CONTENT --> FILTER["Filters"]
    CONTENT --> LIST["Task or Time List"]
    CONTENT --> EMPTY["Empty State"]

    ACTIONS --> ADD_TASK["Add Task"]
    ACTIONS --> ADD_MEMBER["Add Member"]
    ACTIONS --> ARCHIVE["Archive Project"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class HEADER,SUMMARY,TABS,CONTENT,ACTIONS section
    class NAME,CLIENT,STATUS,MANAGER,EDIT,HOURS,BUDGET,MEMBERS,TASK_PROGRESS,OVERVIEW,TASKS,MEMBERS_TAB,TIME,ACTIVITY,SETTINGS,FILTER,LIST,EMPTY,ADD_TASK,ADD_MEMBER,ARCHIVE component
```

---

# 8. Payroll & Payslips

## 8.1 Information Architecture

```mermaid
flowchart TD
    PAYROLL["Payroll & Payslips"]

    PAYROLL --> PERIODS["Payroll Periods"]
    PAYROLL --> PROCESSING["Payroll Processing"]
    PAYROLL --> COMPONENTS["Pay Components"]
    PAYROLL --> PAYSLIPS["Payslips"]
    PAYROLL --> APPROVAL["Payroll Approval"]
    PAYROLL --> SETTINGS["Payroll Settings"]

    PERIODS --> PERIOD_LIST["Payroll Period List"]
    PERIODS --> CREATE_PERIOD["Create Payroll Period"]
    PERIODS --> PERIOD_DETAIL["Payroll Period Detail"]

    PROCESSING --> INPUTS["Payroll Inputs"]
    PROCESSING --> REGULAR_PAY["Regular Earnings"]
    PROCESSING --> OVERTIME_PAY["Overtime Pay"]
    PROCESSING --> ALLOWANCES["Allowances"]
    PROCESSING --> DEDUCTIONS["Deductions"]
    PROCESSING --> TAX["Tax Calculation"]
    PROCESSING --> NET_PAY["Net Salary"]
    PROCESSING --> VALIDATION["Payroll Validation"]

    COMPONENTS --> EARNING_TYPES["Earning Types"]
    COMPONENTS --> DEDUCTION_TYPES["Deduction Types"]
    COMPONENTS --> ALLOWANCE_TYPES["Allowance Types"]

    PAYSLIPS --> GENERATE["Generate Payslips"]
    PAYSLIPS --> PUBLISH["Publish Payslips"]
    PAYSLIPS --> EMPLOYEE_VIEW["Employee Payslip"]
    PAYSLIPS --> DOWNLOAD["Download Payslip"]

    APPROVAL --> REVIEW["Review Payroll"]
    APPROVAL --> APPROVE["Approve Payroll"]
    APPROVAL --> REJECT["Return for Correction"]
    APPROVAL --> LOCK["Lock Payroll"]

    SETTINGS --> CURRENCY["Currency"]
    SETTINGS --> PAY_SCHEDULE["Pay Schedule"]
    SETTINGS --> CALCULATION_RULES["Calculation Rules"]

    classDef root fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef critical fill:#fee2e2,stroke:#dc2626, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAYROLL root
    class PERIODS,PROCESSING,COMPONENTS,PAYSLIPS,APPROVAL,SETTINGS category
    class INPUTS,REGULAR_PAY,OVERTIME_PAY,NET_PAY,VALIDATION,GENERATE,PUBLISH,EMPLOYEE_VIEW,REVIEW,APPROVE,LOCK critical
    class PERIOD_LIST,CREATE_PERIOD,PERIOD_DETAIL,ALLOWANCES,DEDUCTIONS,TAX,EARNING_TYPES,DEDUCTION_TYPES,ALLOWANCE_TYPES,DOWNLOAD,REJECT,CURRENCY,PAY_SCHEDULE,CALCULATION_RULES page
```

## 8.2 UI Hierarchy — Payroll Processing

```mermaid
flowchart TD
    PAGE["Payroll Processing Page"]

    PAGE --> HEADER["Payroll Header"]
    PAGE --> STEPPER["Processing Steps"]
    PAGE --> SUMMARY["Payroll Summary"]
    PAGE --> TABLE["Employee Payroll Table"]
    PAGE --> VALIDATION["Validation Panel"]
    PAGE --> FOOTER["Payroll Actions"]

    HEADER --> PERIOD["Payroll Period"]
    HEADER --> STATUS["Payroll Status"]
    HEADER --> LAST_UPDATED["Last Updated"]
    HEADER --> OWNER["Payroll Owner"]

    STEPPER --> INPUT["1. Collect Inputs"]
    STEPPER --> CALCULATE["2. Calculate"]
    STEPPER --> REVIEW["3. Review"]
    STEPPER --> APPROVE["4. Approve"]
    STEPPER --> PUBLISH["5. Publish"]

    SUMMARY --> EMPLOYEES["Employees"]
    SUMMARY --> GROSS["Gross Pay"]
    SUMMARY --> DEDUCTIONS["Deductions"]
    SUMMARY --> NET["Net Pay"]

    TABLE --> SEARCH["Employee Search"]
    TABLE --> FILTER["Error/Department Filter"]
    TABLE --> EMPLOYEE["Employee"]
    TABLE --> REGULAR["Regular Pay"]
    TABLE --> OVERTIME["Overtime"]
    TABLE --> ALLOWANCE["Allowances"]
    TABLE --> DEDUCTION["Deductions"]
    TABLE --> NET_SALARY["Net Salary"]
    TABLE --> ROW_ACTION["Review Details"]

    VALIDATION --> ERROR["Errors"]
    VALIDATION --> WARNING["Warnings"]
    VALIDATION --> SUCCESS["Validated Records"]

    FOOTER --> SAVE["Save Draft"]
    FOOTER --> RECALCULATE["Recalculate"]
    FOOTER --> SUBMIT["Submit for Approval"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class HEADER,STEPPER,SUMMARY,TABLE,VALIDATION,FOOTER section
    class PERIOD,STATUS,LAST_UPDATED,OWNER,INPUT,CALCULATE,REVIEW,APPROVE,PUBLISH,EMPLOYEES,GROSS,DEDUCTIONS,NET,SEARCH,FILTER,EMPLOYEE,REGULAR,OVERTIME,ALLOWANCE,DEDUCTION,NET_SALARY,ROW_ACTION,ERROR,WARNING,SUCCESS,SAVE,RECALCULATE,SUBMIT component
```

---

# 9. Activity Monitoring

## 9.1 Information Architecture

```mermaid
flowchart TD
    ACTIVITY["Activity Monitoring"]

    ACTIVITY --> SCREENSHOT["Screenshots"]
    ACTIVITY --> APP_USAGE["Application Usage"]
    ACTIVITY --> URL_USAGE["Website Usage"]
    ACTIVITY --> PRODUCTIVITY["Productivity"]
    ACTIVITY --> PRIVACY["Privacy & Tracking Settings"]

    SCREENSHOT --> MY_SCREENSHOTS["My Screenshots"]
    SCREENSHOT --> TEAM_SCREENSHOTS["Team Screenshots"]
    SCREENSHOT --> SCREENSHOT_DETAIL["Screenshot Detail"]
    SCREENSHOT --> DELETE_SCREENSHOT["Delete Screenshot"]

    APP_USAGE --> APP_REPORT["Application Usage Report"]
    APP_USAGE --> APP_CATEGORIES["Application Categories"]

    URL_USAGE --> URL_REPORT["Website Usage Report"]
    URL_USAGE --> URL_CATEGORIES["Website Categories"]

    PRODUCTIVITY --> ACTIVITY_LEVEL["Activity Level"]
    PRODUCTIVITY --> PRODUCTIVE_TIME["Productive Time"]
    PRODUCTIVITY --> IDLE_TIME["Idle Time"]
    PRODUCTIVITY --> PRODUCTIVITY_REPORT["Productivity Report"]

    PRIVACY --> CAPTURE_INTERVAL["Screenshot Interval"]
    PRIVACY --> BLUR["Blur Screenshots"]
    PRIVACY --> TRACK_APPS["Track Applications"]
    PRIVACY --> TRACK_URLS["Track Websites"]
    PRIVACY --> RETENTION["Evidence Retention"]

    classDef root fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class ACTIVITY root
    class SCREENSHOT,APP_USAGE,URL_USAGE,PRODUCTIVITY,PRIVACY category
    class MY_SCREENSHOTS,TEAM_SCREENSHOTS,SCREENSHOT_DETAIL,DELETE_SCREENSHOT,APP_REPORT,APP_CATEGORIES,URL_REPORT,URL_CATEGORIES,ACTIVITY_LEVEL,PRODUCTIVE_TIME,IDLE_TIME,PRODUCTIVITY_REPORT,CAPTURE_INTERVAL,BLUR,TRACK_APPS,TRACK_URLS,RETENTION page
```

## 9.2 UI Hierarchy — Activity Dashboard

```mermaid
flowchart TD
    PAGE["Activity Dashboard"]

    PAGE --> HEADER["Page Header"]
    PAGE --> FILTERS["Global Filters"]
    PAGE --> KPI["Productivity Summary"]
    PAGE --> TIMELINE["Activity Timeline"]
    PAGE --> SCREENSHOTS["Screenshot Gallery"]
    PAGE --> USAGE["App and Website Usage"]

    HEADER --> TITLE["Activity"]
    HEADER --> EXPORT["Export Report"]

    FILTERS --> EMPLOYEE["Employee"]
    FILTERS --> TEAM["Team"]
    FILTERS --> PROJECT["Project"]
    FILTERS --> DATE["Date Range"]

    KPI --> WORKED["Tracked Time"]
    KPI --> ACTIVE["Active Time"]
    KPI --> IDLE["Idle Time"]
    KPI --> SCORE["Activity Score"]

    TIMELINE --> HOURLY["Hourly Activity Bars"]
    TIMELINE --> BREAK_MARKERS["Break Markers"]
    TIMELINE --> IDLE_MARKERS["Idle Markers"]

    SCREENSHOTS --> GRID["Screenshot Grid"]
    SCREENSHOTS --> TIME_LABEL["Capture Time"]
    SCREENSHOTS --> PROJECT_LABEL["Project and Task"]
    SCREENSHOTS --> DETAIL["Open Detail"]

    USAGE --> APP_CHART["Application Chart"]
    USAGE --> URL_CHART["Website Chart"]
    USAGE --> CATEGORY_TABLE["Productivity Categories"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class HEADER,FILTERS,KPI,TIMELINE,SCREENSHOTS,USAGE section
    class TITLE,EXPORT,EMPLOYEE,TEAM,PROJECT,DATE,WORKED,ACTIVE,IDLE,SCORE,HOURLY,BREAK_MARKERS,IDLE_MARKERS,GRID,TIME_LABEL,PROJECT_LABEL,DETAIL,APP_CHART,URL_CHART,CATEGORY_TABLE component
```

---

# 10. Reports & Analytics

## 10.1 Information Architecture

```mermaid
flowchart TD
    REPORTS["Reports & Analytics"]

    REPORTS --> TIME["Time Reports"]
    REPORTS --> ATTENDANCE["Attendance Reports"]
    REPORTS --> LEAVE["Leave Reports"]
    REPORTS --> PAYROLL["Payroll Reports"]
    REPORTS --> PROJECT["Project Reports"]
    REPORTS --> PEOPLE["People Reports"]
    REPORTS --> CUSTOM["Custom Reports"]

    TIME --> TIME_EMPLOYEE["Time by Employee"]
    TIME --> TIME_PROJECT["Time by Project"]
    TIME --> TIME_TASK["Time by Task"]
    TIME --> BILLABLE["Billable Hours"]

    ATTENDANCE --> ATT_SUMMARY["Attendance Summary"]
    ATTENDANCE --> LATE["Late Arrivals"]
    ATTENDANCE --> ABSENCE["Absence Report"]
    ATTENDANCE --> OVERTIME["Overtime Report"]

    LEAVE --> LEAVE_BALANCE["Leave Balances"]
    LEAVE --> LEAVE_USAGE["Leave Usage"]

    PAYROLL --> PAYROLL_SUMMARY["Payroll Summary"]
    PAYROLL --> PAYROLL_COST["Payroll Cost"]
    PAYROLL --> DEDUCTION_REPORT["Deduction Report"]

    PROJECT --> PROJECT_COST["Project Cost"]
    PROJECT --> PROJECT_BUDGET["Budget Utilization"]
    PROJECT --> TEAM_UTILIZATION["Team Utilization"]

    PEOPLE --> HEADCOUNT["Headcount"]
    PEOPLE --> TURNOVER["Employee Turnover"]
    PEOPLE --> EMPLOYMENT_STATUS["Employment Status"]

    CUSTOM --> REPORT_BUILDER["Report Builder"]
    CUSTOM --> SAVED_REPORTS["Saved Reports"]
    CUSTOM --> SCHEDULED_REPORTS["Scheduled Reports"]

    classDef root fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class REPORTS root
    class TIME,ATTENDANCE,LEAVE,PAYROLL,PROJECT,PEOPLE,CUSTOM category
    class TIME_EMPLOYEE,TIME_PROJECT,TIME_TASK,BILLABLE,ATT_SUMMARY,LATE,ABSENCE,OVERTIME,LEAVE_BALANCE,LEAVE_USAGE,PAYROLL_SUMMARY,PAYROLL_COST,DEDUCTION_REPORT,PROJECT_COST,PROJECT_BUDGET,TEAM_UTILIZATION,HEADCOUNT,TURNOVER,EMPLOYMENT_STATUS,REPORT_BUILDER,SAVED_REPORTS,SCHEDULED_REPORTS page
```

## 10.2 UI Hierarchy — Report Page

```mermaid
flowchart TD
    PAGE["Report Page"]

    PAGE --> HEADER["Report Header"]
    PAGE --> FILTERS["Report Filters"]
    PAGE --> SUMMARY["Summary Metrics"]
    PAGE --> VISUALIZATION["Visualization Area"]
    PAGE --> DATA["Data Table"]
    PAGE --> ACTIONS["Report Actions"]

    HEADER --> TITLE["Report Name"]
    HEADER --> DESCRIPTION["Description"]
    HEADER --> LAST_REFRESH["Last Refreshed"]

    FILTERS --> DATE["Date Range"]
    FILTERS --> EMPLOYEE["Employee"]
    FILTERS --> TEAM["Team"]
    FILTERS --> PROJECT["Project"]
    FILTERS --> STATUS["Status"]
    FILTERS --> APPLY["Apply Filters"]

    SUMMARY --> KPI_1["Primary Metric"]
    SUMMARY --> KPI_2["Comparison Metric"]
    SUMMARY --> KPI_3["Trend Metric"]

    VISUALIZATION --> CHART_TYPE["Chart Type"]
    VISUALIZATION --> CHART["Chart"]
    VISUALIZATION --> LEGEND["Legend"]

    DATA --> COLUMNS["Report Columns"]
    DATA --> SORT["Sorting"]
    DATA --> PAGINATION["Pagination"]

    ACTIONS --> EXPORT["Export"]
    ACTIONS --> SAVE["Save Report"]
    ACTIONS --> SCHEDULE["Schedule Report"]
    ACTIONS --> SHARE["Share"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class HEADER,FILTERS,SUMMARY,VISUALIZATION,DATA,ACTIONS section
    class TITLE,DESCRIPTION,LAST_REFRESH,DATE,EMPLOYEE,TEAM,PROJECT,STATUS,APPLY,KPI_1,KPI_2,KPI_3,CHART_TYPE,CHART,LEGEND,COLUMNS,SORT,PAGINATION,EXPORT,SAVE,SCHEDULE,SHARE component
```

---

# 11. Administration

## 11.1 Information Architecture

```mermaid
flowchart TD
    ADMIN["Administration"]

    ADMIN --> COMPANY["Company Settings"]
    ADMIN --> USERS["User Accounts"]
    ADMIN --> ROLES["Roles & Permissions"]
    ADMIN --> POLICIES["Workforce Policies"]
    ADMIN --> INTEGRATIONS["Integrations"]
    ADMIN --> NOTIFICATIONS["Notification Settings"]
    ADMIN --> AUDIT["Audit Logs"]

    COMPANY --> PROFILE["Company Profile"]
    COMPANY --> BRANDING["Branding"]
    COMPANY --> LOCATIONS["Locations"]
    COMPANY --> DEPARTMENTS["Departments"]
    COMPANY --> TEAMS["Teams"]

    USERS --> USER_LIST["User List"]
    USERS --> CREATE_USER["Create User"]
    USERS --> ACTIVATE["Activate User"]
    USERS --> DEACTIVATE["Deactivate User"]
    USERS --> INVITE["Invite User"]

    ROLES --> ROLE_LIST["Role List"]
    ROLES --> CREATE_ROLE["Create Role"]
    ROLES --> PERMISSION_MATRIX["Permission Matrix"]
    ROLES --> ASSIGN_ROLE["Assign Role"]

    POLICIES --> TIME_POLICY["Time Tracking Policy"]
    POLICIES --> LEAVE_POLICY["Leave Policy"]
    POLICIES --> OVERTIME_POLICY["Overtime Policy"]
    POLICIES --> PAYROLL_POLICY["Payroll Policy"]
    POLICIES --> SCREENSHOT_POLICY["Screenshot Policy"]

    INTEGRATIONS --> INTEGRATION_LIST["Integration List"]
    INTEGRATIONS --> CALENDAR["Calendar Integration"]
    INTEGRATIONS --> STORAGE["Storage Integration"]
    INTEGRATIONS --> PAYROLL_PROVIDER["Payroll Provider"]

    NOTIFICATIONS --> CHANNELS["Notification Channels"]
    NOTIFICATIONS --> TEMPLATES["Notification Templates"]
    NOTIFICATIONS --> EVENTS["Notification Events"]

    AUDIT --> AUDIT_LIST["Audit Log List"]
    AUDIT --> USER_ACTIVITY["User Activity"]
    AUDIT --> DATA_CHANGES["Data Changes"]
    AUDIT --> SECURITY_EVENTS["Security Events"]

    classDef root fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef category fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef page fill:#f8fafc,stroke:#94a3b8, color: #000000

    class ADMIN root
    class COMPANY,USERS,ROLES,POLICIES,INTEGRATIONS,NOTIFICATIONS,AUDIT category
    class PROFILE,BRANDING,LOCATIONS,DEPARTMENTS,TEAMS,USER_LIST,CREATE_USER,ACTIVATE,DEACTIVATE,INVITE,ROLE_LIST,CREATE_ROLE,PERMISSION_MATRIX,ASSIGN_ROLE,TIME_POLICY,LEAVE_POLICY,OVERTIME_POLICY,PAYROLL_POLICY,SCREENSHOT_POLICY,INTEGRATION_LIST,CALENDAR,STORAGE,PAYROLL_PROVIDER,CHANNELS,TEMPLATES,EVENTS,AUDIT_LIST,USER_ACTIVITY,DATA_CHANGES,SECURITY_EVENTS page
```

## 11.2 UI Hierarchy — Roles & Permissions

```mermaid
flowchart TD
    PAGE["Role & Permission Page"]

    PAGE --> HEADER["Page Header"]
    PAGE --> ROLE_LIST["Role Navigation"]
    PAGE --> ROLE_INFO["Role Information"]
    PAGE --> MATRIX["Permission Matrix"]
    PAGE --> FOOTER["Actions"]

    HEADER --> TITLE["Roles & Permissions"]
    HEADER --> CREATE["Create Role"]

    ROLE_LIST --> SYSTEM_ROLES["System Roles"]
    ROLE_LIST --> CUSTOM_ROLES["Custom Roles"]
    ROLE_LIST --> SEARCH["Search Roles"]

    ROLE_INFO --> ROLE_NAME["Role Name"]
    ROLE_INFO --> DESCRIPTION["Description"]
    ROLE_INFO --> USER_COUNT["Assigned Users"]
    ROLE_INFO --> EDIT["Edit Role"]

    MATRIX --> MODULE_ROWS["Module Rows"]
    MATRIX --> VIEW["View Permission"]
    MATRIX --> CREATE_PERMISSION["Create Permission"]
    MATRIX --> UPDATE["Update Permission"]
    MATRIX --> DELETE["Delete Permission"]
    MATRIX --> APPROVE["Approve Permission"]
    MATRIX --> SELECT_ALL["Select All"]

    FOOTER --> CANCEL["Cancel"]
    FOOTER --> SAVE["Save Permissions"]

    classDef page fill:#dbeafe,stroke:#2563eb, color: #000000
    classDef section fill:#ede9fe,stroke:#7c3aed, color: #000000
    classDef component fill:#f8fafc,stroke:#94a3b8, color: #000000

    class PAGE page
    class HEADER,ROLE_LIST,ROLE_INFO,MATRIX,FOOTER section
    class TITLE,CREATE,SYSTEM_ROLES,CUSTOM_ROLES,SEARCH,ROLE_NAME,DESCRIPTION,USER_COUNT,EDIT,MODULE_ROWS,VIEW,CREATE_PERMISSION,UPDATE,DELETE,APPROVE,SELECT_ALL,CANCEL,SAVE component
```
