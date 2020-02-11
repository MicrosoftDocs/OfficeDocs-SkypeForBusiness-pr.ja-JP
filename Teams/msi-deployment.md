---
title: Microsoft Endpoint Configuration Manager を使用して MSI を使用して Microsoft Teams をインストールする
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
ms.openlocfilehash: 6f57eeb44fd728d1b656ce13f56cf2c5997805b9
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888366"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする

> [!Tip]
> Windows Desktop Clientの効果、計画や展開の方法については、[Teams Windows Desktop Client](https://aka.ms/teams-clients) のセッションを参照してください。

Microsoft Endpoint Configuration Manager、またはグループポリシー、または広範な展開のためのサードパーティの配布メカニズムを使用するには、管理者がユーザーを選ぶためにチームの一括展開に使用できる MSI ファイル (32 ビットと64ビット) を提供しています。マシン. 管理者はこれらのファイルを使用してリモートで Teams を展開できます。そのため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。 展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します (アプリのインストール後に自動起動を無効にできます。 [以下を参照してください](#disable-auto-launch-for-the-msi-installer))。コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開による効果を得られるようにすることもお勧めします。

MSI ファイルへのリンクを次に示します。


|エンティティ  |32ビット      |64ビット      |
|---------|---------|---------|
|業者     | [32ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|米国連邦政府-GCC     | [32ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|米国連邦政府-GCC 高    | [32ビット](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64ビット](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|米国連邦政府-DoD     | [32ビット](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64ビット](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

Teams は、Office 365 ProPlus の展開に含めることもできます。 詳細については、「 [Office 365 を使用して Microsoft Teams を展開する ProPlus](https://docs.microsoft.com/deployoffice/teams-install)を参照してください。

> [!Note]
> Microsoft Endpoint Configuration Manager の詳細については、「[構成マネージャーとは](https://docs.microsoft.com/configmgr/core/understand/introduction)」を参照してください。

## <a name="deployment-procedure-recommended"></a>展開の手順 (推奨)

1. 最新のパッケージを取得します。
2. MSI が事前に入力した既定値を使用します。
3. 可能な場合、コンピューターに展開します。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft Teams MSI パッケージの仕組み

### <a name="pc-installation"></a>PC のインストール

Teams MSI はインストーラーを Program Files に配置します。 ユーザーが新しい Windows ユーザープロファイルにサインインするたびに、インストーラーが起動され、Teams アプリのコピーがそのユーザーの appdata フォルダーにインストールされます。 ユーザーが既にアプリデータ フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。

更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。 最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。以前のバージョンの MSI パッケージを展開する場合、クライアントは、可能な場合に、(VDI 環境を除く) 自動更新されます。 非常に古いバージョンが展開された場合、MSI は、ユーザーが Teams を使用できるようになる前に、アプリの更新をトリガーします。

> [!Important]
> 既定のインストール場所を変更すると、更新フローが崩れる可能性があるため、お勧めしません。 非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。

#### <a name="target-computer-requirements"></a>対象となるコンピューターの要件

- .NET Framework 4.5 以降
- Windows 7 以降
- Windows Server 2012 R2 以降
- 各ユーザー プロファイルに 3 GB のディスク容量 (推奨)

### <a name="vdi-installation"></a>VDI インストール

VDI に Teams デスクトップアプリを展開する方法の詳細なガイダンスについては、「仮想化された[デスクトップインフラストラクチャの teams](teams-for-vdi.md)」を参照してください。

## <a name="clean-up-and-redeployment-procedure"></a>クリーン アップと展開の手順

ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。 このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します。

1. それぞれのユーザー プロファイルにインストールされている Teams アプリをすべてアンインストールします。
2. アンインストール後、%localappdata%\Microsoft\Teams\ 以下のディレクトリを再帰的に削除します。
3. MSI パッケージをその特定のコンピューターに再展開します。

> [!TIP]
> [Microsoft Teams の展開クリーンアップ](scripts/Powershell-script-teams-deployment-clean-up.md)スクリプトを使用して、構成マネージャーで手順1と2を実行できます。

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>インストール後にチームが自動的に起動しないようにする

MSI の既定の動作では、ユーザーがサインインしてからチームを自動的に開始するとすぐに Teams アプリをインストールすることになります。 ユーザーがインストールした後にチームが自動的に起動しないようにするには、グループポリシーを使ってポリシー設定を設定するか、MSI インストーラーの自動起動を無効にします。

#### <a name="use-group-policy-recommended"></a>グループポリシーを使用する (推奨)

[**インストール後に Microsoft Teams が自動的に起動しないよう**にする] グループポリシー設定を有効にします。 このポリシー設定は、User の microsoft Teams で確認できます。 この方法は、組織のニーズに合わせてポリシー設定をオフまたはオンにすることができるため、お勧めします。

Teams をインストールする前にこのポリシー設定を有効にすると、ユーザーが Windows にログインしてもチームは自動的に開始されません。 ユーザーが初めて Teams にサインインすると、次回ユーザーがログインしたときに自動的にチームが開始されます。

詳細については、「グループポリシーを使用して、[インストール後にチームが自動的に起動しないように](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)する」を参照してください。

> [!CAUTION]
> チームを既に展開していて、このポリシーを設定して Teams の自動開始を無効にしたい場合は、まず、グループポリシーの設定を必要な値に設定してから、チームの [ [autostart reset] スクリプト](scripts/powershell-script-teams-reset-autostart.md)をユーザーごとに実行します。

### <a name="disable-auto-launch-for-the-msi-installer"></a>MSI インストーラーの自動起動を無効にします。

次のように**OPTIONS = "noAutoStart = true"** パラメーターを使用して、MSI インストーラーの自動起動を無効にすることができます。  

32 ビット 版向け

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

64 ビット 版向け

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

ユーザーが Windows にログインすると、Teams が MSI と共にインストールされ、チームを開始するためのショートカットがユーザーのデスクトップに追加されます。 ユーザーが Teams を手動で開始するまで、チームは開始されません。 ユーザーが手動でチームを開始すると、ユーザーがログインするたびにチームが自動的に開始されます。

> [!Note]
> MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。 管理者として実行しても、昇格されたアクセス許可で実行しなければ、インストーラーは自動開始を無効にするオプションを構成できません。
