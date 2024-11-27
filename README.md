# cgs-dev-guidelines
CGS Development Guidelines

## CGS Developer Github Project Workflow

```mermaid
sequenceDiagram
  actor dev as CGS Developer
  participant ghr as CGS Github Repository 
  participant fghr as CGS Developer Remote Repository 
  participant mon as Monday.com Storyboard
  participant lw as CGS Developer Local Repository
  actor sm as Scrum Master
  actor reviewer as CGS Project Github Repository Steward
  dev->>ghr: Fork project repository
  ghr->>fghr: forked
  fghr-->>dev: 
  dev->>fghr: Clone repository
  fghr->>lw: 
  lw-->>dev: 
  sm->>dev: Assign Story
  dev->>lw: Create story-id branch
  loop Make branch changes
     dev->lw: git commit
     dev->>mon: Add story updates
  end
  dev->>lw: git push
  lw->>fghr: 
  fghr-->>dev: 
  dev->>fghr: Create Pull Request (PR)
  fghr->>ghr: 
  ghr->>reviewer: Send PR review notification
  opt Review Status
    reviewer->>dev: Review/Accept
    reviewer->>dev: Review/Reject
  end
```

