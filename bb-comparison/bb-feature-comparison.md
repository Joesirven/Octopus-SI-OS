# BB features compared with Octopus

- BB is version 0.49.0 (changelog dated 2026-11-06). Octopus is commit d372510f on main (2026-11-08).
- BB features come from the BB changelog since 0.0.29 and the BB documents. Every row is a BB feature, so every BB cell has a check mark.
- Octopus marks come from a source search of the Octopus client, kernel, registry, and documents.
- Octopus mark meanings: ✓ means found. Partial means part of the feature exists. Blank means not found in the search. Blank does not prove that the feature is absent.
- Priority meanings: High means reliability, recovery, or a core daily step that Octopus needs now. Medium means a large productivity or reach gain. Low means a small gain, or Octopus already has the feature.
- Totals: 108 features. Octopus has 33, has 32 in part, and lacks 42. 1 is not applicable. Priority: 9 High, 37 Medium, 62 Low.

| Feature | Description | BB | Octopus | Priority | Why Octopus might need it |
|---|---|---|---|---|---|
| **Threads and conversation** | | | | | |
| Steer a running turn | Send a message into the reply that is running to correct the agent mid-turn. | ✓ | ✓ | Low | Octopus already makes steer the default Send action. Keep it reliable across restarts, as BB does. |
| Queue follow-up messages | Hold messages until the current turn ends, then send them in order. | ✓ | ✓ | Low | Octopus has a queued message list with edit and delete. BB also lets a user send one queued message at once, which Octopus can copy. |
| Send later | Schedule a message to send at a set time. | ✓ |  | Low | A user can plan work for after a usage limit resets. Octopus triggers can carry the schedule, so the cost is small. |
| Persistent drafts | Keep unsent composer text for each thread across restarts. | ✓ | Partial | Medium | Octopus keeps draft state in the composer, but persistence across a crash is not confirmed. While Octopus is unstable, a lost draft is a common and avoidable loss. |
| Edit an earlier message | Change a sent message and run the conversation again from that point. | ✓ | Partial | Medium | Octopus edits queued messages and the current reply only. Rewind from an earlier message lets a user recover from a bad turn without a new task. |
| Fork a thread | Copy a conversation into a new thread to try another approach. | ✓ |  | Medium | A user can explore two approaches and keep the first. Octopus checkpoints already give a natural fork point. |
| Compact conversation | Summarize old context to free the context window, on command or automatically. | ✓ |  | High | Long tasks fail when the context window fills. The provider may compact on its own, but Octopus gives the user no control and no record of it. A visible compact action keeps long tasks alive. |
| Clear conversation | Start with empty context in the same thread. | ✓ |  | Low | A user can reset a confused agent without losing the thread, its project, or its settings. |
| Child threads | An agent starts helper threads for parts of a task. | ✓ | Partial | Medium | Octopus shows the subagent activity of the provider. First-class child tasks give Home a durable way to split work that survives restarts. |
| Parent notifications | A child thread reports its final answer to its parent automatically. | ✓ |  | Medium | Without it, a parent must poll its children. Automatic reports make delegated work finish without the user relaying results. |
| Thread handoff | Move a thread to another provider or machine and continue the work. | ✓ |  | Medium | The Octopus handoff code moves file sources, not conversations. Thread handoff lets a user continue when one provider reaches its limit. |
| Side chat | Ask a quick question beside a thread without changing the main conversation. | ✓ |  | Low | A user can check a fact without adding noise to the main task context. |
| Automatic thread titles | Generate a short title from the first message, with a regenerate action. | ✓ | ✓ | Low | Octopus generates titles and supports rename. A regenerate action is the only gap. |
| Rename and pin threads | Rename threads and pin them to the top of the list. | ✓ | ✓ | Low | Octopus has rename, pinning, and manual sort. No work is needed. |
| Nest threads by drag | Drag a thread onto another thread to make it a child. | ✓ |  | Low | Users can group related work by hand. Octopus fixes the hierarchy as Project, Agent, and task. |
| Archive with undo | Archive a thread and undo the action from a notice. | ✓ | Partial | Low | Octopus has archive and restore. An undo notice prevents an accidental archive from becoming a search task. |
| Thread search | Search thread titles and contents. | ✓ | ✓ | Low | Octopus has search in the command menu and the terminal client. No work is needed. |
| Read and unread state | Mark threads that have new activity as unread. | ✓ | ✓ | Low | Octopus shows unread state in the navigation rail. No work is needed. |
| Message links | Link to one message in a thread and open it from anywhere. | ✓ |  | Low | Links let agents and users cite exact evidence. They also make reports and bug filings shorter. |
| Plan mode | Ask the agent to write a plan before it edits anything. | ✓ | Partial | Medium | Octopus ships a plan mode artifact but no visible switch. A plan step reduces wasted runs and makes approval cheaper. |
| Agent questions | The agent asks the user a question with choices and waits for the answer. | ✓ | ✓ | Low | Octopus has operator input requests. No work is needed. |
| Tool approvals | The user approves or denies a tool call before it runs. | ✓ | ✓ | Low | Octopus asks for approval of Model Context Protocol tool calls and policy grants. No work is needed. |
| Attachments and images | Attach files and images to a message and preview them. | ✓ | ✓ | Low | Octopus has attachments, previews, and a lightbox. No work is needed. |
| File mentions | Refer to a project file with @ in the composer. | ✓ | ✓ | Low | Octopus adds file mentions from its file picker. No work is needed. |
| Prompt history | Recall earlier prompts with the arrow keys. | ✓ | Partial | Low | The Octopus terminal client has input history. The desktop composer can reuse the same store. |
| Model and effort picker | Choose the model, reasoning effort, and service tier for each thread. | ✓ | ✓ | Low | Octopus has a provider model picker with effort and service tier. No work is needed. |
| Context window indicator | Show how much of the context window a thread uses. | ✓ | ✓ | Low | Octopus has a context usage indicator. No work is needed. |
| Custom instructions | Add instructions that apply to every thread, for one project or for all. | ✓ | Partial | Medium | Octopus stores memory and skills as artifacts. A plain instructions file per project is easier for users to find and edit. |
| Prompt library | Save prompts and insert them again with a command. | ✓ |  | Low | Repeated prompts become one action. Octopus artifacts can store them. |
| Inline visualizations | The agent renders charts and diagrams inside the conversation. | ✓ | Partial | Low | Octopus renders Mermaid diagrams in messages. Interactive charts are the gap. |
| **Workspace and navigation** | | | | | |
| Split views | Show several threads or panes side by side. | ✓ | ✓ | Low | Octopus has split panes with layouts kept per conversation. No work is needed. |
| Command palette | Find any action or thread from one search box. | ✓ | ✓ | Low | Octopus has a command menu. No work is needed. |
| Rebindable shortcuts | Change the keyboard shortcut of any action. | ✓ | Partial | Low | Octopus has a shortcut settings page and rebinding for gestures. Full key rebinding is not confirmed. |
| Navigation rail | A narrow rail that switches between projects and main views. | ✓ | ✓ | Low | Octopus has a navigation rail with unread marks. No work is needed. |
| Settings search | Search all settings by name and keyword. | ✓ | Partial | Low | Octopus keeps a settings catalog with keywords. A visible search box is the likely gap. |
| Themes and appearance | Choose light or dark themes, density, and code colors. | ✓ | ✓ | Low | Octopus has appearance settings, code themes, and theme sharing. No work is needed. |
| Integrated terminal | Open a terminal in the thread's working folder. | ✓ | ✓ | Low | Octopus has a terminal pane. No work is needed. |
| In-app browser | Open web pages in a pane inside the app. | ✓ | ✓ | Low | Octopus has a browser tab. No work is needed. |
| File editor and viewer | Open, edit, and save project files inside the app. | ✓ | ✓ | Low | Octopus has a Files pane with Save, Discard, and Cancel. No work is needed. |
| Desktop notifications | Notify the user when a turn ends or needs input. | ✓ | ✓ | Low | Octopus has notifications with sound and event settings. No work is needed. |
| Notification modes per thread | Choose to be notified, muted, or alerted for each thread. | ✓ | Partial | Low | Octopus notification settings are global. Per-thread modes stop noise from busy background tasks. |
| Dock badge | Show the count of threads that need attention on the app icon. | ✓ |  | Low | The user sees pending work without opening the app. |
| Menu bar items | Plugins add items to the system menu bar. | ✓ |  | Low | Quick status and actions stay visible while the main window is closed. |
| Keep Awake | Stop the computer from sleeping while agents work. | ✓ | ✓ | Low | Octopus has a power save blocker. No work is needed. |
| Voice transcription | Dictate messages and transcribe audio files. | ✓ | ✓ | Low | Octopus has dictation with retained recordings. No work is needed. |
| **Code review and git** | | | | | |
| Diff review pane | Review changes file by file, mark files as viewed, and filter them. | ✓ | Partial | High | Octopus has a changes pane. Viewed marks and filters make large reviews practical, and review speed decides how much agent work a user can accept. |
| Worktree for each thread | Run each thread in its own git worktree. | ✓ | ✓ | Low | Octopus has a git worktree driver. No work is needed. |
| Worktree include file | Copy chosen ignored files, such as local settings, into each new worktree. | ✓ |  | Medium | New worktrees often fail to build without local files. A list file removes a manual step for every coding task. |
| Setup and teardown scripts | Run a project script when a worktree is created or removed. | ✓ |  | Medium | Dependencies install and ports free up automatically. This removes a common reason a coding run fails at the start. |
| Base branch choice | Choose the branch a new worktree starts from. | ✓ | Partial | Low | Not confirmed in the Octopus client. It matters when a user works on a release branch. |
| Git status display | Show branch, ahead and behind counts, and uncommitted changes. | ✓ | Partial | Medium | The user sees whether agent work is committed and pushed before closing a task. |
| Pull request status | Show the state and checks of the pull request for a thread's branch. | ✓ | Partial | Medium | Octopus has a GitHub connector and a changes alias for pull requests, but no status display. Status in the thread closes the loop from task to merge. |
| Pull request command | Create and inspect pull requests from the command-line tool. | ✓ |  | Low | Agents can open pull requests through one supported path instead of ad hoc scripts. |
| Agent annotations | Agents leave comments on lines of a diff for the user to review. | ✓ |  | Medium | The agent can explain a risky change exactly where it is. Reviews become faster and more precise. |
| **Machines and remote use** | | | | | |
| Multiple machines | One server runs threads on several enrolled computers. | ✓ | Partial | Medium | Octopus has a remote execution driver, but the client manages one local runtime. Several machines let a user move heavy work off a laptop. |
| Remote access | Reach the app from anywhere through an authenticated address. | ✓ |  | Medium | The user can check and steer work away from the desk. The Octopus tunnel code serves Slack and GitHub webhooks only. |
| Port sharing | Share a server that a thread started through an authenticated link. | ✓ |  | Low | The user can open an agent-built preview from a phone or another computer. |
| Web client | Use the app in a web browser. | ✓ |  | Medium | A browser client works on any computer and is the base for remote access. |
| Mobile app | Use the same threads from an iOS or Android app. | ✓ |  | Medium | Answers to agent questions do not wait until the user is back at the Mac. The Octopus phone matches are only viewport presets for site tests. |
| Push notifications | Send phone notifications when a thread needs the user. | ✓ |  | Medium | A paused run waits for minutes instead of hours. |
| Reconnect catch-up | After a dropped connection, the client replays the events it missed. | ✓ | ✓ | Low | Octopus interfaces read with cursors from the ledger. No work is needed. |
| Server move | Move the server and all data to another machine. | ✓ |  | Low | A user can change computers without losing history. Octopus setup files cover part of this. |
| **Providers and accounts** | | | | | |
| Several agent providers | Run Codex, Claude Code, Pi, Cursor, OpenCode, and others side by side. | ✓ | Partial | High | Octopus lists about 35 provider descriptors, but its docs say the preview is one provider deep. A second solid provider removes the single-vendor risk and tests the interface design. |
| Agent Client Protocol agents | Run any agent that speaks the Agent Client Protocol. | ✓ |  | Medium | One adapter opens many agents. This is cheaper than one driver for each product. |
| Account pool | Rotate across several accounts when one reaches its usage limit. | ✓ |  | Medium | Work continues when one account is limited. Octopus can switch accounts by hand, but it does not rotate them. |
| Provider usage display | Show remaining limits, credits, and reset times. | ✓ | ✓ | Low | Octopus shows usage limits and reset times. No work is needed. |
| Automatic retries | Retry a turn after a temporary provider error, with backoff. | ✓ | Partial | High | Octopus offers a manual Try again action. Automatic retry removes the most common reason a user must watch a run. |
| Stuck turn timeout | Detect a turn that stops producing events and end it cleanly. | ✓ | Partial | High | Octopus watches interface processes, but no turn-level timeout is confirmed. A silent stuck turn is the worst failure for an unattended agent. |
| Restart recovery | Continue work after the app or server restarts. | ✓ | ✓ | Low | Octopus is strong here: durable ledger, a keeper process, and turn continuation. Keep it covered by tests. |
| Out-of-memory protection | Limit memory use and recover when the system ends a process for memory. | ✓ |  | High | Agents and Electron use much memory. Without protection, one large run can end the whole runtime. |
| **Automations and coordination** | | | | | |
| Scheduled automations | Run a prompt on a schedule or interval. | ✓ | ✓ | Low | Octopus triggers support cron, interval, once, and quiet period. No work is needed. |
| Script automations | Run a deterministic script on a schedule without a model. | ✓ | Partial | Low | Cheap recurring checks do not need a model call. Octopus triggers start model work today. |
| Resumable workflows | Run multi-agent scripts with phases and history that resume after a crash. | ✓ | Partial | Medium | Octopus execution environments exchange artifacts, but no scripted orchestration surface exists. Workflows make large delegated jobs repeatable. |
| Concurrency limit | Set global and per-machine ceilings on running threads. | ✓ |  | Medium | Too many parallel runs exhaust memory and usage limits. A ceiling protects the computer and the account. |
| Task tracker | A durable task list with comments that agents and users update. | ✓ |  | Medium | Octopus tasks are conversations. A separate work item list keeps the goals and evidence that outlive one conversation. |
| **Plugins and extension** | | | | | |
| Plugin system | Plugins add panes, commands, tools, settings, and agent tools. | ✓ | Partial | Medium | Octopus client extensions add widgets, tabs, inputs, and repairs. Plugins that also add server tools give a stable path for contributors. |
| Plugin software development kit | A typed package and guide to build plugins. | ✓ | Partial | Medium | Octopus documents extension surfaces as contracts. A published package lowers the cost for outside contributors. |
| Plugin marketplaces | Install plugins from official and community marketplaces. | ✓ |  | Medium | The Octopus docs state there is no hosted marketplace. A marketplace is how an ecosystem grows. |
| Plugin safe mode | Start the app with all plugins turned off to recover from a bad plugin. | ✓ |  | High | Home can author extensions and edit the client's own source. When a generated change breaks the client, safe mode is the way back. |
| Model Context Protocol connectors | Agents call tools from external Model Context Protocol servers. | ✓ | ✓ | Low | Octopus runs Model Context Protocol servers as worker environments. No work is needed. |
| Tools exposed to outside agents | Expose the app's own tools to outside agents through a Model Context Protocol server. | ✓ |  | Medium | An agent in another tool, such as an editor, can then use Octopus memory, tasks, and runs. |
| Discoverable plugin commands | Plugins publish commands that the command-line tool lists and runs. | ✓ |  | Low | Agents learn new capabilities from one place instead of from prose. |
| **Bundled tools** | | | | | |
| Memory | Durable notes that agents save and search. | ✓ | ✓ | Low | Octopus stores memory as artifacts. No work is needed. |
| Docs vaults | Shared Markdown knowledge base folders with pull and push. | ✓ |  | Low | Teams keep reference notes next to agent work with conflict protection. |
| Secrets | Store credentials so their values never enter a transcript. | ✓ | Partial | Medium | Octopus policies use secret handles. A user-facing secret store with a command-line path makes safe credential setup routine. |
| Shared skills | Load skills from shared folders on every machine. | ✓ | Partial | Low | Octopus stores skills as artifacts. Shared folders let users reuse skills from other agent tools. |
| Browser automation | Agents drive a headless browser while the user watches a live preview. | ✓ | Partial | Medium | Octopus has a browser driver and a desktop session. A live preview lets the user see and stop browser work. |
| Cookie import | Import browser cookies so automation can use logged-in sessions. | ✓ |  | Low | Agents can work on sites that need a login without the user typing passwords. |
| Cloud AI services | Generate images, video, and speech through a budgeted gateway. | ✓ | Partial | Low | Octopus has an image generation interface. A budget gate stops surprise costs. |
| Cloud sandboxes | Run threads in Modal cloud sandboxes. | ✓ | Partial | Low | Octopus has a container driver. Cloud sandboxes move risky or heavy work off the Mac. |
| Custom environments | Define how a thread's environment is created, including machine plugins. | ✓ | ✓ | Low | Octopus has environment templates and drivers. No work is needed. |
| **Permissions and settings** | | | | | |
| Permission presets | Named sets of approval rules for each thread. | ✓ | ✓ | Low | Octopus has Project access and Full access, plus policy grants. No work is needed. |
| Per-machine permission limit | A machine sets the most a thread may do there. | ✓ | Partial | Medium | Octopus policy grants cover part of this. A hard ceiling per machine protects shared computers. |
| Project environment variables | Set environment variables for all threads in a project. | ✓ |  | Medium | Builds and tools get their settings without editing global shell files. |
| Telemetry with opt-out | Send anonymous usage data, with a switch to turn it off. | ✓ | Not applicable | Low | Octopus has no analytics by design, and a test enforces it. Keep that choice. |
| **Updates and platforms** | | | | | |
| In-app updates | Check, download, and install updates from Settings, when no work is running. | ✓ |  | High | Octopus has no updater. Users stay on builds with known bugs until they reinstall by hand. |
| Release channels | Choose a stable or a nightly channel. | ✓ |  | Low | Testers get fixes early and other users stay stable. |
| Changelog in Settings | Show what changed in each version inside the app. | ✓ |  | Low | Users learn about fixes and new features without leaving the app. |
| Linux desktop | Run the desktop app on Linux. | ✓ |  | Medium | Octopus requires macOS 14 or later. Linux opens the project to more contributors and to servers. |
| Windows desktop | Run the desktop app on Windows. | ✓ |  | Medium | Windows is the largest desktop audience. The Octopus sandbox uses a macOS-only tool, so this needs design work. |
| **Upkeep and recovery** | | | | | |
| Storage retention | Prune old thread data on a schedule, within set limits. | ✓ |  | Medium | The Octopus ledger is append-only, so disk use only grows. Retention keeps long-term use safe. |
| Database maintenance | Repair and compact the database and its indexes. | ✓ | Partial | Medium | Octopus keeps a SQLite index beside the ledger. Scheduled maintenance prevents slow startup and index damage. |
| Persisted format migration | Upgrade stored data automatically when a new version changes its format. | ✓ |  | High | The Octopus docs say persisted formats are not migrated. Every format change can break existing users, which blocks an updater. |
| Diagnostics | Collect a safe report for bug filing. | ✓ | ✓ | Low | Octopus has Report a Problem and a doctor command. No work is needed. |
| Setup guide | Guide a new user through first setup. | ✓ | ✓ | Low | Octopus has a setup wizard and setup files. No work is needed. |
| **Command-line tool and API** | | | | | |
| Full command-line parity | Every feature in the app also works from the command-line tool and the software development kit. | ✓ | Partial | Medium | The Octopus terminal client lacks voice and widgets. Full parity lets agents operate every feature they can see. |
| Terminal command runner | Run a command in a thread's terminal from the command-line tool. | ✓ | Partial | Low | Agents can start and watch long commands in a shared, visible terminal. |
| Documented HTTP API | A stable HTTP API for scripts and other clients. | ✓ |  | Medium | Outside tools and future web or mobile clients need one stable contract. |

## Analysis

- Octopus has 33 of the 108 BB features, has 32 in part, and lacks 42. Most of what it has is in the conversation and the workspace. Most of what it lacks is in reach (remote, mobile, other platforms), upkeep, and the plugin ecosystem.
- Suggested order for the High items: first the reliability work (automatic retries, the stuck turn timeout, and out-of-memory protection).
- Next, persisted format migration. Do this before in-app updates, because an updater is not safe while each new version can break stored data.
- Then the daily-use gaps: the diff review pane, compact conversation, a second solid provider, and plugin safe mode.
- Octopus is ahead of BB in restart recovery, the movement ledger, verifiers, and the deny-by-default sandbox. A contribution must not weaken these.
- Every BB check mark was confirmed in the BB changelog or the BB source. Octopus marks come from a source search, so confirm a blank mark in the running app before you start work on it.

## Features only Octopus has

| Feature | Description | Note for BB |
|---|---|---|
| Movement ledger | Every action is an append-only movement in a ledger with a SQLite index. | BB could gain an audit trail that survives any crash. |
| Verifiers and marks | Verifiers check artifacts, and marks record the result. | BB could gate task completion on a machine check, not on agent claims. |
| Deny-by-default sandbox | Runs execute under a macOS sandbox profile with explicit grants. | BB could tighten local execution beyond approval prompts. |
| Self-review with change journal | A trigger reviews the system, records each change in a journal, and supports undo. | BB could let agents improve conventions with a safe undo. |
| Home-authored extensions | The Home conversation writes new client extensions and edits the client source. | BB could let users grow the app by asking for it. |
| Message triggers | Incoming email, Telegram, or Slack messages start work. | No message-based trigger was found in BB automations. |
| Setup files | Export and import a whole setup as one file. | BB could make a new machine match an old one in one step. |
| Voice calls | Talk with Home in a live voice call. | No voice call feature was found in BB. BB has voice recording and transcription. |
| Gesture control | Experimental hand gestures run client commands. | This is an accessibility and hands-free option. |
| Lock screen | Lock the app with a password or Touch ID. | No app lock was found in BB. |
| Review task | Start a review of one task's work by another agent. | BB has diff review for people. No built-in agent review step was found. |
