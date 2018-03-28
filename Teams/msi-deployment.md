---
title: MSI を使用してマイクロソフトのチームをインストールします。
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: 管理者が一括してチームの msi ファイルを使用できますユーザーまたはコンピューターを選択するのには、マイクロソフトのチームを配置します。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a>MSI を使用してマイクロソフトのチームをインストールします。
===========================================

システム センター構成マネージャーで、またはグループ ポリシーでは、広範な展開に、サード パーティ配布メカニズムを活用して、マイクロソフトは管理者の一括展開時に活用するための MSI ファイル ( [32 ビット](http://aka.ms/teams32bitmsi)と[64 ビット](http://aka.ms/teams64bitmsi)の両方) を提供します。ユーザーまたはコンピューターを選択するのにはマイクロソフトのチームです。 管理者は、これらのファイルを使用して、リモートで展開するチームのユーザーがチームのアプリケーションを手動でダウンロードする必要はありません。 展開されると、チームが自動的にそのコンピューターでサインインするすべてのユーザーに対して起動します。 マシンにすべての新しいユーザーは、この展開からな利点がありますので、コンピューターにパッケージを展開することをお勧めします。 
 
> [!Note] 
> SCCM の詳細についてを参照してください。 [System Center 構成マネージャー](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a>展開手順 (推奨)
1. 最新のパッケージを取得します。
2. MSI によって事前設定の既定値を使用します。
3. 可能な場合は、マシンへの導入します。

## <a name="how-the-microsoft-teams-msi-package-works"></a>マイクロソフト チームの MSI パッケージが機能するしくみ

チームの msi ファイルには、プログラム ファイルのインストーラーが配置されます。 ユーザーが新しい Windows ユーザー プロファイルにサインインするたびに、インストーラーが起動され、チームのアプリケーションのコピーをそのユーザーの appdata フォルダーにインストールされます。 Appdata フォルダーにインストールされているチームのアプリケーションがユーザーに割り当てられている場合、MSI インストーラーはそのユーザーのプロセスをスキップします。

更新を展開する msi ファイルを活用していない、クライアントが自動的に更新プログラムの新しいバージョンがサービスから利用可能なを検出したとき。 再配置するのには、最新のインストーラーは、以下に示す MSI を再配置のプロセスを使用します。 以前のバージョンの MSI パッケージを展開する場合、クライアントは自動更新可能な場合は、ユーザーのです。 非常に古いバージョンを取得を展開する場合、ユーザーはチームを使用するのには、前に msi ファイルはアプリケーションの更新をトリガーします。 

> [!Important] 
> いない任意のインストール場所を変更する更新プログラムの流れが切れることがこれをお勧めします。 最終的にブロックされますから、サービスにアクセスするユーザー。 


## <a name="target-machine-requirements"></a>ターゲット マシンの要件:

1. 4.5 またはそれ以降の .NET framework
2. Windows 7 またはそれ以降
2. 32 GB (推奨)、各ユーザー プロファイル用のディスク領域の

## <a name="clean-upredeployment-procedure"></a>Up\redeployment プロシージャを削除します。
それぞれのユーザー プロファイルからのチームをアンインストールすると、MSI インストーラーは、ユーザーがチームのアプリケーションがアンインストールされ、不要になったチームをそのユーザーのプロファイルのインストールに追跡します。 特定のコンピューターにこのユーザーをアンインストールするためにチームを再展開するには、必要があります。

1. チーム アプリケーションのすべてのユーザー プロファイルのインストールをアンインストールします。 
2. アンインストール後、ディレクトリを再帰的に %localappdata%\Microsoft\Teams\ の下の削除 
3. その特定のコンピューターに MSI パッケージを再展開します。

> [!TIP] 
> SCCM を使用してこの手順 1 と 2 を実行する[マイクロソフトのチームの配置のクリーンアップ](.\scripts\Powershell-script-teams-deployment-clean-up.md)スクリプトを活用することができます。                                

