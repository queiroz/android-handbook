# MDX rendering contract

The handbook repository owns content. The private DevBits site owns presentation.

To remain portable, handbook MDX may use standard Markdown plus the components documented here. It must not import private homepage components, site configuration, database code, or private utilities.

## Supported components

- `ShortAnswer`
- `InterviewerNotes` (legacy placeholder support)
- `SeniorAnswer`
- `CommonMistake`
- `SeniorDetail`
- `TradeOff`
- `FollowUp`
- `RealWorldExample`
- `Exercise`
- `ReferenceList`
- `ThinkAboutIt`
- `KeyTakeaways`
- `Remember`
- `PlatformStack`
- `AndroidStackMap`
- `RuntimeProcessMap`
- `CameraRequestFlow`
- `ApiPathMap`

These components accept Markdown children and no required props. Content must remain understandable when reading the raw MDX source.

## Compatibility rules

- Primary section titles remain Markdown headings.
- Components provide emphasis, not document structure.
- Assets use stable handbook-owned paths.
- Custom interactive components require an explicit contract update.
- No component may require authentication, client-side persistence, or a database.
