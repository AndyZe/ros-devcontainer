# ros-devcontainer

Paste these files into .devcontainer

It's likely this will be used as part of another git repository. To avoid having this included, add the .devcontainer folder to .git/info/exclude (which works like a local .gitignore)

Note: for joystick, ros2 uses /dev/input/event*, which the default user does not have read access to. To correct the user permissions, ros-activate.sh finds the group that owns the file, and adds the current user to that group.

Note: Create the ccache folder manually from outside the container, or suffer user permission errors.
If Docker creates the folder it will be owned by root:root and ccache will not have permission to run. To fix this, make the ccache folder in the workspace before using or:

```
sudo chown stephanie:stephanie ccache
```

from outside the container, or:

```
sudo chown user:user /home/user/.ccache
```