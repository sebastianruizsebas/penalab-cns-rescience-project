# flyresponse-replication

A computational neuroscience model replication project focused on fly visual response systems.

## Table of Contents

- [Contributing with Pull/Merge Requests](#contributing-with-pullmerge-requests)
- [Maintaining a Private Research Journal](#maintaining-a-private-research-journal)

## Contributing with Pull/Merge Requests

Follow these steps to create and submit pull/merge requests:

1. **Create a new branch** from the main branch for your work:
   ```bash
   git checkout main
   git pull origin main
   git checkout -b your-feature-branch
   ```

2. **Make your changes** in the new branch, committing regularly with clear, descriptive commit messages:
   ```bash
   git add <modified-files>
   git commit -m "Brief description of changes"
   ```

3. **Keep your branch up to date** with the main branch to avoid merge conflicts:
   ```bash
   git checkout main
   git pull origin main
   git checkout your-feature-branch
   git merge main
   ```

4. **Push your branch** to the remote repository:
   ```bash
   git push origin your-feature-branch
   ```

5. **Create a Pull/Merge Request** on GitHub/GitLab:
   - Navigate to the repository on the web interface
   - Click "New Pull Request" or "New Merge Request"
   - Select your feature branch as the source and main as the target
   - Provide a clear title and description of your changes
   - Reference any related issues using `#issue-number`

6. **Request reviews** from team members and address any feedback:
   - Make additional commits to your branch to address comments
   - Push updates to automatically update the PR/MR

7. **Merge your request** once approved:
   - Ensure all CI/CD checks pass
   - Use "Squash and merge" or "Merge commit" as per team conventions
   - Delete the feature branch after merging

8. **Update your local repository** after merging:
   ```bash
   git checkout main
   git pull origin main
   git branch -d your-feature-branch
   ```

## Maintaining a Private Research Journal

A research journal is a valuable tool for documenting your thoughts, experiments, observations, and insights throughout the project. Here's how to maintain one effectively while keeping it private:

### Getting Started

1. **Create your journal file** in the project root or a dedicated directory:
   ```bash
   touch research-journal.md
   # or
   mkdir journal && touch journal/research-journal.md
   ```

2. **Structure your journal** with clear sections and dates:
   ```markdown
   # Research Journal
   
   ## [Date: YYYY-MM-DD]
   
   ### Experiments
   - Description of experiment
   - Parameters used
   - Results observed
   
   ### Insights
   - Key findings
   - Questions raised
   
   ### Next Steps
   - Planned experiments
   - Items to investigate
   ```

### Best Practices

- **Date your entries**: Always include timestamps for each entry
- **Be detailed**: Include experiment parameters, code snippets, and specific observations
- **Link to commits**: Reference relevant commits by their SHA when documenting code-related insights
- **Include visualizations**: Embed or reference plots, graphs, and diagrams
- **Track hypotheses**: Document what you're testing and why
- **Record failures**: Failed experiments are as valuable as successes
- **Note resources**: Keep track of papers, documentation, and external resources consulted

### Keeping Your Journal Private

To prevent your research journal from being committed to the main branch, use these methods:

#### Method 1: Using .gitignore (Recommended)

1. **Create or edit** the `.gitignore` file in the project root:
   ```bash
   # Create .gitignore if it doesn't exist
   touch .gitignore
   ```

2. **Add your journal files** to `.gitignore`:
   ```
   # Private research journals
   research-journal.md
   *-journal.md
   journal/
   notes/
   .personal/
   ```

3. **Verify it's ignored**:
   ```bash
   git status  # Your journal should not appear in untracked files
   ```

#### Method 2: Using .git/info/exclude (Personal)

For personal exclusions that you don't want to share with the team:

1. **Edit** `.git/info/exclude`:
   ```bash
   nano .git/info/exclude
   ```

2. **Add your journal pattern**:
   ```
   research-journal.md
   my-notes.md
   ```

This method keeps the exclusion local to your repository clone only.

#### Method 3: Use a Separate Branch (Advanced)

1. **Create a personal journal branch**:
   ```bash
   git checkout -b personal/research-journal
   ```

2. **Commit your journal** to this branch only:
   ```bash
   git add research-journal.md
   git commit -m "Update research journal"
   ```

3. **Never merge this branch** into main - keep it separate for your records

#### Verifying Your Journal is Private

Before committing, always check:

```bash
# Check what would be committed
git status

# Check what's being tracked
git ls-files | grep -i journal

# Verify your .gitignore is working
git check-ignore -v research-journal.md
```

### Team Collaboration on Journals

While individual journals should remain private, consider:

- **Shared insights document**: Create a separate `INSIGHTS.md` or `FINDINGS.md` for team-wide learnings
- **Meeting notes**: Use a `meetings/` directory for collaborative documentation
- **Experiment logs**: Create a shared experiment tracking system separate from personal journals

### Template for Journal Entries

```markdown
## [Date: 2026-01-31]

### Goals for Today
- [ ] Task 1
- [ ] Task 2

### Experiments Conducted

#### Experiment: [Name]
**Hypothesis**: 
**Method**: 
**Parameters**: 
**Results**: 
**Conclusion**: 

### Code Changes
- Commit: [SHA] - [Description]
- Files modified: 

### Insights & Questions
- Insight 1
- Question 1

### Tomorrow's Plan
- Item 1
- Item 2

### References
- Paper/Link 1
- Paper/Link 2
```

## License

This project is licensed under CC0 1.0 Universal. See the [LICENSE](LICENSE) file for details.
