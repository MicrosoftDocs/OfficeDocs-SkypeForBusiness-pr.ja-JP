---
title: MSI を使用して Microsoft Teams をインストールする
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理者は Teams MSI を使用して、Microsoft Teams を選択したユーザーまたはコンピューターに一括展開することができます。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882039"
---
<a name="install-microsoft-teams-using-msi"></a>MSI を使用して Microsoft Teams をインストールする
=================================

System Center Configuration Manager、またはグループ ポリシー、または任意のサードパーティの配布メカニズムを広範囲の展開に使用するために、マイクロソフトは管理者が選択したユーザーまたはコンピューターへの Teams の一括展開で使用することができる MSI ファイル ([32-bit](https://aka.ms/teams32bitmsi) と [64-bit](https://aka.ms/teams64bitmsi) の両方) を提供しています。 管理者はこれらのファイルを使用してリモートで Teams を展開することができます。このため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。 展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します。 コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開のメリットを得られるようにすることをお勧めします。 
 
> [!Note] 
> SCCM の詳細については、「[System Center Configuration Manager の概要](https://docs.microsoft.com/sccm/core/understand/introduction)」をご覧ください。

## <a name="deployment-procedure-recommended"></a>展開の手順 (推奨)
1. 最新のパッケージを取得します。
2. MSI によって事前に入力された既定値を使用します。
3. 可能な場合、コンピューターに展開します。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft Teams MSI パッケージがどのように機能するか

Teams MSI はインストーラーを Program Files に配置します。 ユーザーが新しい Windows ユーザー プロファイルにサインインするときは常に、インストーラーが起動して Teams アプリケーションのコピーがそのユーザーのアプリデータ フォルダーにインストールされます。 ユーザーが既にアプリデータ フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。

更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。 最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。 MSI パッケージの以前のバージョンを展開すると、クライアントは自動更新をそのユーザーで可能なときに実行します。 かなり昔のバージョンが展開された場合、MSI はユーザーが Teams を使用できる状態になる前にアプリケーションの更新を開始します。 

> [!Important] 
> 既定のインストール場所を変更することは、更新フローが崩れる可能性があるため、お勧めしません。 かなり昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。 


## <a name="target-computer-requirements"></a>ターゲット コンピューターの要件

- .NET Framework 4.5 以降
- Windows 7 以降
- 各ユーザー プロファイルで 3 GB のディスク容量 (推奨)

## <a name="clean-up-and-redeployment-procedure"></a>クリーン アップと展開の手順
ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。 このユーザーのために Teams がアンインストールされた特定のコンピューター上でユーザーを再展開するには、次の手順を実行します。

1. それぞれのユーザー プロファイルでインストールされている Teams アプリをすべてアンインストールします。 
2. アンインストール後、%localappdata%\Microsoft\Teams\ 以下のディレクトリを再帰的に削除します。 
3. MSI パッケージをその特定のコンピューターに再展開します。

> [!TIP] 
> [Microsoft Teams の展開のクリーン アップ](.\scripts\Powershell-script-teams-deployment-clean-up.md) スクリプトを使用して、SCCM を介して手順 1 と 2 を完了することができます。                              

