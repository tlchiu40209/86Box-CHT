# 86Box 繁體中文版

---

要下載預先編譯好 (For Windows x64) 的版本，請直接 [Release](https://github.com/tlchiu40209/86Box-CHT/releases) 下載。  
解壓縮後即可使用。

![86BoxCHT](https://raw.githubusercontent.com/tlchiu40209/86Box-CHT/main/image/Screenshot.png "86Box Traditional Chinese Screenshot")


由於繁體中文語言檔案尚未 Pull Request 給作者，**若您使用 [WinBox for 86Box](https://github.com/tlchiu40209/WinBox-for-86Box-CHT) 繁體中文版，請記得在程式設定中關閉「模擬器自動更新」**，否則 86Box 繁體中文版會被複寫過去，則變回原本的英文版。

另外在某些 Windows 環境中，程式無法自動選擇正確的介面的語言，請手動透過工具列「Tools」->「Preference」中，將語言改為 Chinese (Traditional, Taiwan)

若使用 WinBox 時，86Box 沒有使用正確的語言啟動時，請注意 WinBox 設定中「**語言**」的設定

---

86Box 是由 **OBattler** 開發的 x86 模擬器軟體，其原本是一個由 PCem 分支出來的專案 PCem-X，而後成為現在的 86Box。  
目標與 PCem 相同，提供一個僅可能還原從 1981 到 Pentium II 時代的 x86 平台，包含主機板、處理器、音效卡等各式硬體。

目前 86Box 已由多個核心人員共同維護。

關於 86Box 更多的說明請見:
- [86Box](http://86box.net/)
- [86Box Github](https://github.com/86Box/86Box)

本專案以中文化 86Box 介面為目的，無實質新增其他功能。  
由於新增語言仍然需要修改部份原始碼檔案，才能使新增的繁體中文選項出現在選單中，並非直接新增一個語言檔案即可，故在繁體中文化尚未整合進 86Box 之前，請不要試圖 Merge，否則會發生沒有此語言選項的問題。

---

中文化 86Box 參照版本: [86Box 3.3 Build 3721 (42f9e49)](https://github.com/86Box/86Box/commit/42f9e49a3ad36164d42abaf9d9696ce69874f964)

編譯平台: Windows 7 x64 / Visual Studio 2015 (VC14) / MSYS2

---

如果您要自行編譯這個專案，而不下載預先編譯版本:

Windows 作業系統 (MinGW)  
1. 安裝 MSYS2，並啟動相對應環境 (如 MSYS2 MinGW x64)，第一次啟動時，請先進行更新 :
```sh
pacman -Syuu
```
2. 安裝基礎編譯環境:
```sh
pacman -Syu base-devel gcc clang
```
3. 安裝相關涵式庫 FreeType, libpng, RtMidi, SDL2, FAudio (Windows 上可選), Qt5 或 Qt6 (如果不想依賴 Windows 的使用者介面涵式庫) (安裝時請注意對應)
```sh
pacman -Syu $MINGW_PACKAGE_PREFIX $MINGW_PACKAGE_PREFIX-ninja $MINGW_PACKAGE_PREFIX-cmake $MINGW_PACKAGE_PREFIX-gcc $MINGW_PACKAGE_PREFIX-pkg-config $MINGW_PACKAGE_PREFIX-openal $MINGW_PACKAGE_PREFIX-freetype $MINGW_PACKAGE_PREFIX-SDL2 $MINGW_PACKAGE_PREFIX-zlib $MINGW_PACKAGE_PREFIX-libpng $MINGW_PACKAGE_PREFIX-rtmidi $MINGW_PACKAGE_PREFIX-qt5-static $MINGW_PACKAGE_PREFIX-qt5-translations
```
4. 在 Source Code 目錄執行
```sh
$ cmake -D CMAKE_TOOLCHAIN_FILE=./cmake/flags-gcc-x86_64.cmake -B <編譯目錄> -S <原始碼目錄>
例如: cmake -D CMAKE_TOOLCHAIN_FILE=./cmake/flags-gcc-x86_64.cmake -B build -S ./
完成後:
$ cmake --build <編譯目錄>
例如: cmake --build build
```

關於 Build 的詳細說明，請見 [86Box Documentation - Building Guide](https://86box.readthedocs.io/en/latest/dev/buildguide.html) 頁面。

---

原作者已使用 GPL v2.0 授權該軟體之使用，詳情請見 COPYING 檔案。  
其中所使用之 [munt](https://github.com/munt/munt), [FluidSynth](https://www.fluidsynth.org/), [Ghostscript](https://www.ghostscript.com/), [Discord Game SDK](https://discord.com/developers/docs/game-sdk/sdk-starter-guide) 則依照該組件所設定之授權為準

---