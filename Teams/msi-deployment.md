---
title: Teams インストーラー (MSI) をWindows一括インストールする
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Windows インストーラー (MSI) ファイルを使用して、クライアントTeams複数のユーザーとコンピューターに配布します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fc9e17f958b1770573cf6729ef6aca9b22ffe03d
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893566"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>Teams インストーラー (MSI) をWindows一括インストールする

> [!Tip]
> Windows Desktop Client の効果、計画や展開の方法については、[Teams Windows Desktop Client](https://aka.ms/teams-clients) のセッションを参照してください。

Microsoft では、32 ビット、64 ビット、および ARM64 MSI ファイルを提供しています。このファイルを使用して、Microsoft Teams を一括展開してユーザーとコンピューターを選択できます。 MSI ファイルは、[Microsoft Endpoint Configuration Manager グループ ポリシー](/configmgr/core/understand/introduction)、またはサード パーティ[](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)の配布ソフトウェアと一緒に使用して、組織にTeams展開できます。 一括デプロイは、ユーザーがクライアントを手動でダウンロードしてインストールする必要がTeams便利です。 コンピューターにTeamsユーザーがコンピューターに初めてサインインすると、自動的に起動されます。

特定のユーザーではなく、コンピューターにパッケージを展開することをお勧めします。 コンピューターを対象とすることで、これらのコンピューターのすべての新しいユーザーが、この展開のメリットを得る効果があります。

>[!NOTE]
> Teamsの一部として組織に配布Microsoft 365 Apps for enterprise。 詳細については、「[Microsoft 365 Apps for enterprise で Microsoft Teams を展開する](/deployoffice/teams-install)」をご覧ください。

## <a name="msi-files"></a>MSI ファイル

次の表は、32 ビット、64 ビット、ARM64 MSI ファイルへのリンクを示Teams。 組織のコンピューターにインストールする MSI をダウンロードします。 x86 アーキテクチャ (32 ビットまたは 64 ビット) Teamsは、コンピューターにインストールされている他の Office アプリとは独立しています。

64 ビット版のコンピューターがある場合は、コンピューターで 32 ビット版の Office を実行している場合でも、64 ビット Teams MSI をインストールすることをお勧めします。 ARM64 MSI は、X などの ARM アーキテクチャを使用するコンピューターにのみSurface Proできます。

> [!IMPORTANT]
> 64 ビット版のオペレーティング システムTeams 64 ビット版のみをインストールします。 32 ビットオペレーティング システムに 64 ビットバージョンの Teams をインストールしようとしても、インストールは成功し、エラー メッセージは表示されません。

|エンティティ  |32 ビット      |64 ビット      | ARM64 |
|---------|---------|---------|-----------|
|商用     | [32 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|米国政府機関 - GCC     | [32 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 ビット](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|米国政府機関 - GCC High    | [32 ビット](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 ビット](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|米国政府機関 - DoD     | [32 ビット](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 ビット](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>MSI ファイルMicrosoft Teamsのしくみ

### <a name="pc-installation"></a>PC インストール

このTeams MSI は、`%SystemDrive%\Program Files\Teams Installer`インストーラーを 32 ビット`%SystemDrive%\Program Files (x86)\Teams Installer`の Windows と 64 ビットのアプリケーションにWindows。 ユーザーが新しい Windows ユーザー プロファイルにサインインすると、インストーラーが起動され、そのユーザーのフォルダーに Teams アプリのコピーがインストール`%LocalAppData%\Microsoft\Teams`されます。 ユーザーがフォルダーに既に Teams アプリ`%LocalAppData%\Microsoft\Teams`をインストールしている場合、MSI インストーラーは、そのユーザーのプロセスをスキップします。

MSI ファイルを使用して更新プログラムをデプロイできません。 新しいTeamsがサービスから利用できると検出されると、クライアントは自動的に更新されます。 最新のインストーラーを再デプロイするには、以下で説明する MSI を再デプロイするプロセスを使用します。 以前のバージョンの MSI ファイルをデプロイした場合、クライアントは(VDI 環境を除く) ユーザーに対して可能な限り自動更新されます。 非常に昔のバージョンが展開された場合、MSI はユーザーが Teams を使用できる状態になる前にアプリの更新をトリガーします。

> [!IMPORTANT]
> 既定のインストール場所を変更すると、更新フローが壊れる可能性があります。 非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。

#### <a name="target-computer-requirements"></a>対象となるコンピューターの要件

インストールするコンピューターが、「ハードウェア要件」にTeams要件を満たしていることを[確認](hardware-requirements-for-the-teams-app.md)Microsoft Teams。

### <a name="vdi-installation"></a>VDI インストール

VDI に Teams デスクトップ アプリを展開する方法の詳細なガイダンスについては、「[仮想デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md)」を参照してください。

## <a name="clean-up-and-redeployment-procedure"></a>クリーン アップと展開の手順

ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。 このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します:

> [!IMPORTANT]
> 以下の手順では、レジストリの変更方法について説明します。 レジストリの変更前にレジストリをバックアップし、問題が発生した場合にレジストリを復元する方法を知っておいてください。 レジストリのバックアップ、復元、および編集方法については、「[上級ユーザー向けの Windows レジストリ情報](https://support.microsoft.com/help/256986)」を参照してください。

1. それぞれのユーザー プロファイルにインストールされている Teams アプリをすべてアンインストールします。 詳細については、「[Microsoft Teams のアンインストール](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)」を参照してください。
2. 各ユーザー プロファイルの 下の ディレクトリ `%LocalAppData%\Microsoft\Teams\` を再帰的に削除します。
3. 各ユーザー `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` プロファイルのレジストリ値を削除します。
4. その特定のコンピューターに MSI ファイルを再デプロイします。

> [!TIP]
> [Teams の展開のクリーン アップ スクリプト](scripts/powershell-script-deployment-cleanup.md)を使用して、手順 1 と 2 を完了することができます。  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>インストール後に Teams が自動的に起動しないようにする

MSI の既定の動作では、ユーザーがサインインするとすぐに Teams アプリがインストールされ、Teams が自動的に起動されます。 ユーザーがインストールした後に Teams が自動的に起動しないようにするには、グループ ポリシーを使用してポリシー設定を設定するか、MSI インストーラーの自動起動を無効にします。

### <a name="use-group-policy-recommended"></a>グループ ポリシーを使用する (推奨)

[インストール **後にMicrosoft Teamsグループ ポリシーが自動的に開始されるの**[を防ぐ] 設定を有効](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)にします。 このポリシー設定は、**User** **ConfigurationPoliciesAdministrative**\\\\ **Templates**\\ にMicrosoft Teams。 組織のニーズに合わせてポリシー設定を無効にも有効にもできるため、この方法を使用することをお勧めします。

Teams がインストールされる前にこのポリシー設定を有効にしていると、ユーザーが Windows にログインしても Teams は自動起動しません。 ユーザーが初めて Teams にサインインすると、次にユーザーがログインしたときに Teams が自動起動するようになります。

詳細については、「[グループ ポリシーを使用してインストール後に Microsoft Teams の自動起動を回避する](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)」を参照してください。

> [!CAUTION]
> Teams を展開済みで、このポリシー設定で Teams の自動起動を無効にするには、最初にグループ ポリシー設定を必要な値に設定してから、ユーザーごとに [Teams 自動起動リセット スクリプト](scripts/powershell-script-teams-reset-autostart.md)を実行します。

### <a name="disable-auto-launch-for-the-msi-installer"></a>MSI インストーラーの自動起動を無効にする

MSI インストーラーの自動起動は、次のように パラメーターを使用 `OPTIONS="noAutoStart=true"` して無効にできます。  

32 ビット版向け:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

64 ビット版向け:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

ユーザーが Windows にログインすると、Teams は MSI と一緒にインストールされ、Teams を起動するためのショートカットがユーザーのデスクトップに追加されます。 そのユーザーが手動で Teams を起動するまで Teams は起動しません。 ユーザーが手動で Teams を起動すると、そのユーザーがログインするたびに Teams は自動起動するようになります。

これらの例でも **ALLUSERS=1** パラメーターを使用していることに注意してください。 このパラメーターを設定すると、コンピューターのすべてのユーザーの [コントロール パネル] の [プログラムと機能] および [Windows の設定] の [アプリと機能] に Teams Machine-Wide Installer が表示されます。 コンピューターに管理者資格情報がある場合、すべてのユーザーは Teams をアンインストールできます。

> [!Note]
> MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。 管理者として実行する場合でも、管理者特権で実行しない限り、インストーラーで自動起動を無効にするオプションを構成することはできません。
