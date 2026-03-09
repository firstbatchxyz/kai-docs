# Team Collaboration

Work together with your team to review, triage, and resolve security vulnerabilities. The web dashboard makes it easy to coordinate security efforts across your organization.

## Inviting Team Members

Add colleagues to your workspace to collaborate on security findings.

<video
  autoPlay
  muted
  loop
  playsInline
  className="w-full aspect-video"
  src="/images/manage workspace members_web.mov"
/>

### How to Invite

1. Navigate to your workspace settings
2. Click **Team Members**
3. Click **Invite Member**
4. Enter their email address
5. Select their role (Viewer, Member, or Admin)
6. Click **Send Invitation**

Invited users receive an email with a link to join your workspace.

## Team Roles

### Viewer
- View all scan results and vulnerability details
- Read exploit reports and fix suggestions
- Cannot run scans or modify vulnerability status

**Best for**: Stakeholders, managers, compliance officers

### Member
- Everything Viewers can do, plus:
- Run new security scans
- Update vulnerability status on the Kanban board
- Add comments and notes to findings

**Best for**: Developers, security engineers, QA team members

### Admin
- Everything Members can do, plus:
- Invite and remove team members
- Modify workspace settings
- Manage repository configurations

**Best for**: Team leads, security managers, project owners

## Collaborative Workflows

### Vulnerability Assignment

Assign vulnerabilities to specific team members for resolution:

1. Open a vulnerability from the Kanban board
2. Click **Assign**
3. Select a team member
4. They'll receive a notification

### Communication

Team members can:
- Add comments to specific vulnerabilities
- @mention colleagues for attention
- Track discussion history on each finding

### Notifications

Stay informed about important security events:
- **Email notifications** when scans start and complete
- Vulnerabilities assigned to you
- Status changes on findings you're watching

Kai automatically sends email notifications for scan lifecycle events. You'll receive an email when an execution begins and another when results are ready for review.

## Best Practices

### Security Triage Meeting

Schedule regular meetings to review new findings:
1. Filter Kanban by "Awaiting Approval" status
2. Review each finding as a team
3. Assign ownership and priority
4. Move to appropriate workflow column

### Ownership Model

Establish clear ownership:
- **Security Team**: Reviews all Critical/High findings first
- **Development Team**: Owns fixing assigned vulnerabilities
- **Team Lead**: Manages workflow and priorities

### Documentation

Use comments to document:
- Decision rationale for "Won't Do" items
- Fix verification notes
- Related findings or context

## Next Steps

- [Vulnerability Management](vulnerability-management) - Master the Kanban workflow
- [Analytics](analytics) - Track team performance metrics
