---
title: 仲介サーバーのファイルをサーバーにインストールSkype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '概要: 仲介サーバー用のファイルをインストールする方法について説明します。Skype for Business Server。'
ms.openlocfilehash: e74c966cc43b9768b107aff559429eb8a639e2cd
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397450"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>仲介サーバーのファイルをサーバーにインストールSkype for Business Server
 
**概要:** 仲介サーバー用のファイルをインストールする方法については、Skype for Business Server。
  
この手順を正常に完了するには、少なくともローカル管理者および少なくとも RTCUniversalReadOnlyAdmins グループにメンバーシップを持つドメイン ユーザーとして、サーバーにログオンする必要があります。
  
このトピックの手順を使用して、Skype for Business Server 展開ウィザードを実行して、トポロジ ビルダーを使用してプールを定義および発行した後に仲介サーバー プールに追加したコンピューターに仲介サーバーのファイルをインストールします。 ファイル仲介サーバーをインストールする場合は、仲介サーバー プール内の各コンピューターに必要な証明書をインストールして割り当てることもできます。 
  
> [!NOTE]
> このトピックでは、「Skype for Business Server のトポロジ ビルダーでの仲介サーバーの展開」の説明に従って、スタンドアロンの仲介サーバー プールをトポロジで既に定義して公開済[みと仮定します](deploy-a-mediation-server.md)。 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>スタンドアロン仲介サーバー プールのファイルをインストールするには

1. インストール メディアで、[管理者] を右クリック  _\<installation media\>_ **\Setup\amd64\Setup.exe** し、[管理者として **実行] をクリックします**。
    
2. [インストール場所 **] ページで、[** OK] を **クリックします**。
    
3. [エンド **ユーザー 使用許諾契約書] ページで** 、[同意する] **をクリックし**、[OK] を **クリックします**。 (続行するには必須)。
    
4. [展開ウィザード **Skype for Business Server] ページで**、[システムのインストールまたは **更新] Skype for Business Serverクリックします**。
    
5. [手順 **1: ローカル構成ストアのインストール] の** 横にある [ **実行**] をクリックし、画面の指示に従います。
    
6. [中央 **管理ストアのローカル レプリカの** 構成] ページで、既定の **[** 中央管理ストアから直接取得] を受け入れ、[次へ] をクリック **します**。
    
7. [コマンドの **実行] ページ** で、タスクの状態が [完了] と表示されている場合は **、[完了]** をクリック **します**。
    
8. [手順 **2: コンポーネントのセットアップまたは削除] の横Skype for Business Server[****実行**] をクリックし、[次へ] を **クリックします**。
    
9. [コマンドの **実行] ページ** で、タスクの状態が [完了] と表示されている場合は **、[完了]** をクリック **します**。
    
10. [手順 **3: 証明書の要求、インストール、** または割り当て] の横にある [実行] を **クリックします**。 画面の指示に従って、既定の設定を受け入れる。 仲介サーバーには 1 つの証明書が必要なので、手順 **3 を 2** 回実行します。必要な証明書を発行するには 1 回、割り当てるにはもう一度実行します。
    
11. 証明書が発行され、正しく割り当てられたら、[手順 **4: サービス** の開始] の横にある [実行] をクリックし、画面の指示に従います。
    
12. 手順 **4 が** 正常に完了したら、サーバーを再起動し、DomainAdmins グループのメンバーとしてサーバーにログオンします。
    
13. Skype for Business Server コントロール パネルを実行しているコンピューターで、Skype for Business Server コントロール パネルの [トポロジ]  ページで、仲介サーバーのサービス状態が緑色のチェック マークとして表示されます。 代わりに赤い X が表示される場合は、仲介サーバーを選択します。 [操作] **メニューの** [すべてのサービスの **開始] をクリックします**。 
    
仲介サーバー プールに複数のコンピューターを追加した場合は、仲介サーバー プール内の他のすべてのコンピューターで、この手順の手順を実行します。 他のコンピューターに仲介サーバー用のファイルをインストールする必要がない場合は、「[Skype for Business Server](configure-trunks.md) のトランクの構成」の手順に従って、この仲介サーバー プール (またはサイト内のすべての仲介サーバー) とそのピア間のトランク接続の設定を構成します。

