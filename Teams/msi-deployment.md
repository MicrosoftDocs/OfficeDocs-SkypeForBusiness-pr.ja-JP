---
title: MSI を使用して SCCM 経由で Microsoft Teams をインストールする
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理者は Teams MSI を使用して、Microsoft Teams を選択したユーザーまたはコンピューターに一括展開することができます。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5ffceef19e91f5d3e694db7655d23efb67498ae
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464349"
---
<a name="install-microsoft-teams-using-msi"></a>MSI を使用して Microsoft Teams をインストールする
=================================

> [!Tip]
> Windows Desktop Clientの効果、計画や展開の方法については、[Teams Windows Desktop Client](https://aka.ms/teams-clients) のセッションを参照してください。

System Center Configuration Manager、またはグループ ポリシー、または任意のサードパーティの配布メカニズムを広範囲の展開に使用するために、マイクロソフトは管理者が選択したユーザーまたはコンピューターへの Teams の一括展開で使用できる MSI ファイル ([32 ビット](https://aka.ms/teams32bitmsi)と [64 ビット](https://aka.ms/teams64bitmsi)の両方) を提供しています。 管理者はこれらのファイルを使用してリモートで Teams を展開できます。そのため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。 展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します (アプリのインストール後に自動起動を無効にできます。 [以下を参照してください](#disable-auto-lanuch-for-the-msi-installer))。コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開による効果を得られるようにすることもお勧めします。 
 
> [!Note] 
> SCCM の詳細については、「[System Center Configuration Manager の概要](https://docs.microsoft.com/sccm/core/understand/introduction)」を参照してください。

## <a name="deployment-procedure-recommended"></a>展開の手順 (推奨)
1. 最新のパッケージを取得します。
2. MSI が事前に入力した既定値を使用します。
3. 可能な場合、コンピューターに展開します。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft Teams MSI パッケージの仕組み

Teams MSI はインストーラーを Program Files に配置します。 ユーザーが新しい Windows ユーザー プロファイルにサインインするときは常に、インストーラーが起動して Teams アプリケーションのコピーがそのユーザーのアプリデータ フォルダーにインストールされます。 ユーザーが既にアプリデータ フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。

更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。 最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。MSI パッケージの以前のバージョンを展開すると、クライアントはそのユーザーが可能なときに自動更新を実行します。 非常に昔のバージョンが展開された場合、MSI はユーザーが Teams を使用できる状態になる前にアプリケーションの更新を開始します。 

> [!Important] 
> 既定のインストール場所を変更すると、更新フローが崩れる可能性があるため、お勧めしません。 非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。 


## <a name="target-computer-requirements"></a>対象となるコンピューターの要件

- .NET Framework 4.5 以降
- Windows 7 以降
- 各ユーザー プロファイルに 3 GB のディスク容量 (推奨)

## <a name="clean-up-and-redeployment-procedure"></a>クリーン アップと展開の手順
ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。 このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します。

1. それぞれのユーザー プロファイルにインストールされている Teams アプリをすべてアンインストールします。 
2. アンインストール後、%localappdata%\Microsoft\Teams\ 以下のディレクトリを再帰的に削除します。 
3. MSI パッケージをその特定のコンピューターに再展開します。

> [!TIP] 
> [Microsoft Teams の展開のクリーン アップ](scripts/Powershell-script-teams-deployment-clean-up.md) スクリプトを使用して、SCCM を介して手順 1 と 2 を完了することができます。    
                    
## <a name="disable-auto-launch-for-the-msi-installer"></a>MSI インストーラーの自動起動を無効にします。

MSI の既定の動作では、ユーザーがサインインするとすぐに Teams クライアントをインストールしてから自動的に Teams を起動します。 次のように、以下のパラメーターを使用してこの動作を変更できます。

- ユーザーが Windows にログインする場合、Teams が MSI と一緒にインストールされる
- ただし、ユーザーが Teams を手動で開始するまで、Teams のクライアントは起動しない
- Teams を起動するショートカットは、ユーザーのデスクトップに追加される
- 手動で開始すると、ユーザーがログインするたびに Teams が自動的に起動する

32 ビット 版向け
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
64 ビット 版向け
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```
> [!Note] 
>  MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。 昇格されたアクセス許可がなく、管理者として実行する場合でも、インストーラーは自動起動を無効にするオプションを構成できません。
