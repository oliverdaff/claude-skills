# `/expert-review add` flow

When the user invokes `/expert-review add` (with or without a name), walk them through building their panel:

1. **Show current roster** — list current experts by category with a one-line summary each
2. **Identify gaps** — based on the user's typical work (check project CLAUDE.md, recent conversation context), suggest 2-3 domains that are underrepresented. Examples: "You have no security expert", "No one covers database design", "Your frontend coverage is thin"
3. **Ask what they want to add** — let the user name someone, describe a domain they want covered, or pick from your suggestions
4. **For each expert to add:**
   - If you recognise the person: pre-fill their focus, flags, and "Ask:" question. Show the draft and ask the user to confirm or tweak
   - If you don't recognise them: ask the user three questions:
     - What's their focus/domain?
     - What do they typically flag or criticise?
     - What's the core question they'd ask about any piece of work?
   - Ask which roster category to place them in (suggest one, let user override)
5. **Write to roster.md** — append the new entry in the existing format, under the chosen category
6. **Confirm** — show what was added and the updated category listing

The user can add multiple experts in one session — loop back to step 3 until they're done.
