# AGENTS.md — proxmox-perfect-woocommerce

Gemeinsame Instruktionsdatei für alle Agenten (Claude, Codex, Gemini); `CLAUDE.md` ist ein
Symlink hierauf. Globale Regeln: `~/Developer/KI/neo.md`.

**Öffentliches Produkt** (`github.com/greecro/proxmox-perfect-woocommerce`): **ein** Script auf
dem Proxmox-Host, legt einen unprivilegierten LXC an und führt darin
[`greecro/perfect-woocommerce`](https://github.com/greecro/perfect-woocommerce) aus.
Details: [README.md](README.md) (englisch).

## Projektregeln

1. **Nur der Wrapper.** Stack-Logik gehört nach `perfect-woocommerce`.
2. **Öffentliches Repo, fremde Proxmox-Hosts.** Keine IPs, Gast-IDs, Storage- oder Bridge-Namen
   aus Danys Cluster, auch nicht als Default.
3. **Änderungen gegen `proxmox-perfect-wordpress` spiegeln** — die beiden Wrapper sind bewusst
   identisch aufgebaut, nur die Ressourcen-Vorgaben unterscheiden sich.
4. **Debian-13-Kompatibilität ist hart erarbeitet:** `sudo` vorinstallieren, Locale korrekt
   erzeugen, `apt` mit `LANG=C`, `systemd-run` beachten. Diese Zeilen nicht „vereinfachen" —
   jede hat einen konkreten Fehlschlag als Ursache.
5. **Nach dem Installieren eines Binaries `hash -r`.**
6. **An die Prompts des Installers gekoppelt** — bei Änderungen beide Repos zusammen prüfen.
