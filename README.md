# Shtil VPN — Scoop bucket

Install [Shtil VPN](https://shtil.ndvsdom54.ru/) for Windows:

```powershell
scoop bucket add shtil https://github.com/narvinIR/scoop-shtil
scoop install shtil-vpn
```

Scoop unpacks the release installer instead of running it, so the app lands in the
Scoop directory and leaves the registry alone. Later updates come with
`scoop update shtil-vpn`. The app can also update itself, but on a Scoop install let
Scoop do it — otherwise the two disagree about which version is current.

To remove it:

```powershell
scoop uninstall shtil-vpn
```

Settings and the key stay in `%APPDATA%\app.realityvpn.desktop`; `scoop uninstall -p`
removes those too.

## What it is

A Tauri desktop client built on the [sing-box](https://github.com/SagerNet/sing-box)
core: VLESS + Reality over TCP, a system-wide TUN tunnel, and route splitting done on
the device, so sites in the user's own country keep the direct path while the tunnel is
up. Routing lists are compiled into the app instead of being fetched at runtime. The
core ships inside the package — nothing is downloaded on first run.

Windows 10 and newer, 64-bit. macOS builds live in the
[Homebrew tap](https://github.com/narvinIR/homebrew-shtil); the download page is
[shtil.ndvsdom54.ru](https://shtil.ndvsdom54.ru/).

- Source: [narvinIR/shtil-vpn-desktop](https://github.com/narvinIR/shtil-vpn-desktop) (MIT)
- Guides: [shtil.ndvsdom54.ru/en/guides/](https://shtil.ndvsdom54.ru/en/guides/)
- Key and support: [@RealityVPNBot_bot](https://t.me/RealityVPNBot_bot)

## First launch

The build is signed with the publisher's own key, not with a certificate Windows
recognises, so Defender may move it to quarantine —
[the walkthrough is here](https://shtil.ndvsdom54.ru/en/guides/windows-warning/).
