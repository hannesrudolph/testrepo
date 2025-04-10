# Active Context

---

## Development Coordination

### Current Development Focus
 
- Improve inline editing UI for Name/Email/Notes/Timezone in ContributorsTable (current implementation deemed unsatisfactory).

### Cross-Component Dependencies

- Modal state management through ModalContext affects both GitHub and Discord linking components
- Platform user selection data should be properly isolated between different modal instances

### Technical Debt Items

- Need to ensure proper state cleanup when modals are closed to prevent data leakage between components
- API Key "Reload Credit" button in ContributorsTable expanded row does not trigger balance update despite UI and backend logic appearing correct.

### Recently Completed
- Fixed Discord role assignment error (`Cast to ObjectId failed` in backend API).
- Investigated Discord user synchronization mechanism; confirmed automated API usage.
- Updated `techContext.md` and `progress.md` to reflect automated Discord sync via API.
- Implemented inline Discord role assignment UI and functionality within the Contributors Table.


- Enhanced Discord user display (avatar fallback, display name format) in Discord Integration view (`ContributorsManagement.tsx`).
- Stored Discord `displayName` in `DiscordUser` model and updated backend service.
- Fixed 'Cast to ObjectId failed' error during Discord unlinking in `contributorLinkService.ts`.
- Applied consistent Discord display pattern (avatar fallback, name format) to Current Contributors table (`ContributorsTable.tsx`).
- Updated backend `Contributor` model and repository to embed `displayName` in `discordUsers` array.
- Fixed modal state persistence bug by properly resetting modal state in ModalContext.tsx
- State now fully resets when modals are closed, preventing cross-contamination between platform-specific modals
- Added conditional field disabling for GitHub/Discord user fields in ContributorModal
- Platform fields are now only disabled when coming from specific platform creation flows
- Fixed regression where GitHub/Discord fields were incorrectly disabled on default contributor creation.
- Resolved React Hooks order error in `ContributorsManagement.tsx`.
- Fixed GitHub linking modal bug ("No GitHub user selected" error):
  - Refactored `GitHubLinkingModal.tsx` to handle both pre-selected (context) and internally selected GitHub users.
  - Resolved type conflicts between `Contributor`, `GitHubUser`, and `PlatformUser`.
  - Corrected filtering logic in `usePlatformData.ts` hook to fix user selector issue.
- Implemented backend models, repositories, service, controller, and routes for API Key and Balance Transaction management.
- Implemented frontend API service (`apiKeyAPI.ts`) and types (`ApiKeyInfo`, `BalanceTransaction`).
- Added Timezone display and inline editing to ContributorsTable expanded row.
- Added API Key info display, "Add Key" functionality, and Reload Credit UI to ContributorsTable expanded row.
- Refined expandable row mechanism and layout in ContributorsTable.
- Debugged and fixed various TypeScript and runtime errors introduced during feature implementation.

