---
title: MSI を使用して Microsoft Teams をインストールする
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理者は Teams MSI を使用して、Microsoft Teams を選択したユーザーまたはコンピューターに一括展開することができます。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4983f8089a5d221a29f67ae25dfa6766751a7394
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530591"
---
<a name="install-microsoft-teams-using-msi"></a>MSI を使用して Microsoft Teams をインストールする
=================================

> [!Tip]
> Windows デスクトップ クライアント、それを計画する方法および展開方法の利点について説明するのには次のセッションを監視する:[チームの Windows デスクトップ クライアント](https://aka.ms/teams-clients)

マイクロソフトは MSI ファイル ( [32 ビット](https://aka.ms/teams32bitmsi)と[64 ビット](https://aka.ms/teams64bitmsi)の両方) を選択するのにはチームの一括展開の管理者が使用できるを提供する広範な展開のシステム センター構成マネージャーでは、グループ ポリシー、または任意のサードパーティ製の配布メカニズムを使用して、ユーザーまたはコンピューターです。 管理者は、これらのファイルを使用して、リモートで展開するチームのユーザーがチームのアプリケーションを手動でダウンロードする必要はありません。 展開されると、チームが自動的にそのコンピューター上でサインインしているすべてのユーザーに対して起動します。 (アプリケーションのインストール後の自動起動を無効にします。 [以下を参照してください](#disable-auto-lanuch-for-the-msi-installer))。マシンのすべての新しいユーザーは、この展開からな利点がありますので、コンピューターにパッケージを展開することをお勧めします。 
 
> [!Note] 
> SCCM の詳細については、[システム センター構成マネージャーの概要](https://docs.microsoft.com/sccm/core/understand/introduction)を参照してください。

## <a name="deployment-procedure-recommended"></a>(推奨) の展開手順
1. 最新のパッケージを取得します。
2. MSI によって事前設定の既定値を使用します。
3. 可能な場合にコンピューターに展開します。

## <a name="how-the-microsoft-teams-msi-package-works"></a>マイクロソフト チームの MSI パッケージが機能するしくみ

チームの msi ファイルには、プログラム ファイルのインストーラーが配置されます。 ユーザーが新しい Windows ユーザー プロファイルにサインインするたびに、インストーラーが起動され、チームのアプリケーションのコピーをそのユーザーの appdata フォルダーにインストールされます。 Appdata フォルダーにインストールされているチームのアプリケーションがユーザーに割り当てられている場合、MSI インストーラーはそのユーザーのプロセスをスキップします。

クライアントが自動的に更新プログラムの新しいバージョンがサービスから利用可能なを検出したときのため、更新プログラムを展開する MSI を使わないでください。 再配置するのには、最新のインストーラーは、以下に示す MSI を再配置のプロセスを使用します。以前のバージョンの MSI パッケージを展開する場合、クライアントは自動更新可能な場合は、ユーザーのです。 非常に古いバージョンを取得を展開する場合、ユーザーはチームを使用するのには、前に msi ファイルはアプリケーションの更新をトリガーします。 

> [!Important] 
> この更新プログラムの流れが切れることは、デフォルトのインストール先を変更することお勧めしないです。 非常に古いバージョンを持つと、ユーザーがサービスにアクセスする、最終的にブロックします。 


## <a name="target-computer-requirements"></a>対象のコンピューターの要件

- 4.5 またはそれ以降の .NET framework
- Windows 7 またはそれ以降
- 3 GB (推奨)、各ユーザー プロファイル用のディスク領域の

## <a name="clean-up-and-redeployment-procedure"></a>クリーンアップと再配置の手順
ユーザー プロファイルからチームをアンインストールすると、MSI インストーラーは、ユーザーがチームのアプリケーションがアンインストールされ、不要になったチームをそのユーザーのプロファイルのインストールに追跡します。 アンインストールされた特定のコンピューターにこのユーザーのチームを再配置する、次の操作を行います。

1. チーム アプリケーションのすべてのユーザー プロファイルのインストールをアンインストールします。 
2. アンインストール後、% の localappdata%\Microsoft\Teams\ の下を再帰的にディレクトリを削除します。 
3. その特定のコンピューターに MSI パッケージを再展開します。

> [!TIP] 
> SCCM を使用して、手順 1 と 2 を実行するのには、[マイクロソフトのチームの配置のクリーンアップ](scripts/Powershell-script-teams-deployment-clean-up.md)スクリプトを使用できます。    
                    
## <a name="disable-auto-launch-for-the-msi-installer"></a>MSI インストーラーの自動起動を無効にします。

Msi ファイルの既定の動作では、ユーザーがサインインすると、すぐにチームのクライアントをインストールし、チームを自動的に開始します。 次のようにこの動作は以下のパラメーターを変更できます。

- チームを msi ファイルをインストールするユーザーが Windows にログインするとき
- ただし、チームのクライアントが起動しない、ユーザーがチームを手動で開始されるまで
- チームを起動するショートカットをユーザーのデスクトップに追加されます。
- 手動で開始されると、チームは自動的に開始、ユーザーがログインするたびに

32 ビット バージョンの
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
64 ビット バージョンの
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```
> [!Note] 
>  Msi ファイルを手動で実行する場合は、昇格されたアクセス許可を使用して実行することを確認します。 実行する場合でも、管理者は、昇格されたアクセス許可で実行することがなく、インストーラーを自動開始を無効にするオプションを構成することはできません。
