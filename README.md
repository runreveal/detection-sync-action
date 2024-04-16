# RunReveal Detection Sync

A Github Action that will sync a given directory to your RunReveal detections in the supplied workspace.

## Usage

```yaml
- name: sync-runreveal-detections
  uses: runreveal/detection-sync-action@v1
  with:
    # The directory containing the detections you want to sync.
    # Should be absolute path or relative to your current directory.
    # Defaults to your current directory
    directory: ./detections

    # A RunReveal API token generated with detection edit permissions
    # For best results generate your token with the `cibot` role. 
    token: ${{ secrets.RUNREVEAL_TOKEN }}

    # The RunReveal workspace ID to sync the detections with.
    # This workspace should match the workspace the token was generated under.
    workspace: ${{ vars.RUNREVEAL_WORKSPACE }}

    # Include this input to perform a dry run of the sync process.
    # This will verify your detections without making any changes.
    dry-run: true
```