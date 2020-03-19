---
title: Microsoft Endpoint Configuration Manager から MSI を使用して Microsoft Teams をインストールする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 管理者は Teams MSI を使用して、Microsoft Teams を選択したユーザーまたはコンピューターに一括展開することができます。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c048e321241f4403fbb69f71e56b3fc179346951
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327829"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする

> [!Tip]
> Windows Desktop Clientの効果、計画や展開の方法については、[Teams Windows Desktop Client](https://aka.ms/teams-clients) のセッションを参照してください。

Microsoft Endpoint Configuration Manager、またはグループ ポリシー、または任意のサードパーティの配布メカニズムを広範囲の展開に使用するために、マイクロソフトは管理者が選択したユーザーまたはコンピューターへの Teams の一括展開で使用できる MSI ファイル (32 ビットと 64 ビットの両方) を提供しています。 管理者はこれらのファイルを使用してリモートで Teams を展開できます。そのため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。 展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します (アプリのインストール後に自動起動を無効にできます。 [以下を参照してください](#disable-auto-launch-for-the-msi-installer))。コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開による効果を得られるようにすることもお勧めします。

MSI ファイルへのリンクを次に示します。


|エンティティ  |32 ビット      |64 ビット      |
|---------|---------|---------|
|商用     | [32 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|政府機関向け - GCC     | [32 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|政府機関向け - GCC High    | [32 ビット](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 ビット](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|政府機関向け - DoD     | [32 ビット](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 ビット](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

Teams は、Office 365 ProPlus の展開に含まれる場合があります。 詳細については、「[Office 365 ProPlus で Microsoft Teams を展開する](https://docs.microsoft.com/deployoffice/teams-install)」をご覧ください。

> [!Note]
> Microsoft Endpoint Configuration Manager について詳しくは、「[Configuration Manager とは](https://docs.microsoft.com/configmgr/core/understand/introduction)」を参照してください。

## <a name="deployment-procedure-recommended"></a>展開の手順 (推奨)

1. 最新のパッケージを取得します。
2. MSI が事前に入力した既定値を使用します。
3. 可能な場合、コンピューターに展開します。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft Teams MSI パッケージの仕組み

### <a name="pc-installation"></a>PC インストール

Teams MSI はインストーラーを Program Files に配置します。 ユーザーが新しい Windows ユーザー プロファイルにサインインするときは常に、インストーラーが起動して Teams アプリのコピーがそのユーザーの `AppData` フォルダーにインストールされます。 ユーザーが既に `AppData` フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。

更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。 最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。 MSI パッケージの以前のバージョンを展開すると、クライアントはそのユーザーが可能なときに自動更新を実行します (VDI 環境を除く)。 非常に昔のバージョンが展開された場合、MSI はユーザーが Teams を使用できる状態になる前にアプリの更新をトリガーします。

> [!Important]
> 既定のインストール場所を変更すると、更新フローが崩れる可能性があるため、お勧めしません。 非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。

#### <a name="target-computer-requirements"></a>対象となるコンピューターの要件

- .NET Framework 4.5 以降
- Windows 8.1 以降
- Windows Server 2012 R2 以降
- 各ユーザー プロファイルに 3 GB のディスク容量 (推奨)

### <a name="vdi-installation"></a>VDI インストール

VDI に Teams デスクトップ アプリを展開する方法の詳細なガイダンスについては、「[仮想デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md)」を参照してください。

## <a name="clean-up-and-redeployment-procedure"></a>クリーン アップと展開の手順

ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。 このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します。

1. それぞれのユーザー プロファイルにインストールされている Teams アプリをすべてアンインストールします。
2. アンインストール後、`%localappdata%\Microsoft\Teams\` 以下のディレクトリを再帰的に削除します。
3. MSI パッケージをその特定のコンピューターに再展開します。

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>インストール後に Teams が自動的に起動しないようにする

MSI の既定の動作では、ユーザーがサインインするとすぐに Teams アプリがインストールされ、Teams が自動的に起動されます。 ユーザーがインストールした後に Teams が自動的に起動しないようにするには、グループ ポリシーを使用してポリシー設定を設定するか、MSI インストーラーの自動起動を無効にします。

#### <a name="use-group-policy-recommended"></a>グループ ポリシーを使用する (推奨)

**[Prevent Microsoft Teams from starting automatically after installation]**(インストール後に Microsoft Teams が自動的に起動しないようにする) グループ ポリシー設定を有効にします。 このポリシー設定は、[ユーザー構成]\[ポリシー]\[管理用テンプレート]\[Microsoft Teams] にあります。 組織のニーズに合わせてポリシー設定を無効にも有効にもできるため、この方法を使用することをお勧めします。

Teams がインストールされる前にこのポリシー設定を有効にしていると、ユーザーが Windows にログインしても Teams は自動起動しません。 ユーザーが初めて Teams にサインインすると、次にユーザーがログインしたときに Teams が自動起動するようになります。

詳細については、「[グループ ポリシーを使用してインストール後に Microsoft Teams の自動起動を回避する](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)」を参照してください。

> [!CAUTION]
> Teams を展開済みで、このポリシー設定で Teams の自動起動を無効にするには、最初にグループ ポリシー設定を必要な値に設定してから、ユーザーごとに [Teams 自動起動リセット スクリプト](scripts/powershell-script-teams-reset-autostart.md)を実行します。

### <a name="disable-auto-launch-for-the-msi-installer"></a>MSI インストーラーの自動起動を無効にする

次のように **OPTIONS="noAutoStart=true"** パラメーターを使用することにより、MSI インストーラーの自動起動を無効にできます。  

32 ビット 版向け

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

64 ビット 版向け

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

ユーザーが Windows にログインすると、Teams は MSI と一緒にインストールされ、Teams を起動するためのショートカットがユーザーのデスクトップに追加されます。 そのユーザーが手動で Teams を起動するまで Teams は起動しません。 ユーザーが手動で Teams を起動すると、そのユーザーがログインするたびに Teams は自動起動するようになります。

> [!Note]
> MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。 管理者として実行する場合でも、管理者特権で実行しない限り、インストーラーで自動起動を無効にするオプションを構成することはできません。
