---
title: Skype for Business Server に仲介サーバーのファイルをインストールする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '概要: Skype for Business Server で仲介サーバーのファイルをインストールする方法について説明します。'
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830797"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Skype for Business Server に仲介サーバーのファイルをインストールする
 
**概要:** Skype for Business Server で仲介サーバーのファイルをインストールする方法について説明します。
  
この手順を正常に完了するには、少なくとも、ローカル管理者および少なくとも RTCUniversalReadOnlyAdmins グループのメンバーシップを持つドメイン ユーザーとしてサーバーにログオンする必要があります。
  
このトピックの手順を使用して、Skype for Business Server 展開ウィザードを実行して、トポロジ ビルダーを使用してプールを定義および公開した後に仲介サーバー プールに追加したコンピューターに仲介サーバーのファイルをインストールします。 ファイル仲介サーバーをインストールする場合は、仲介サーバー プール内の各コンピューターに必要な証明書もインストールして割り当てる必要があります。 
  
> [!NOTE]
> このトピックでは [、Skype for Business Server](deploy-a-mediation-server.md)のトポロジ ビルダーでの仲介サーバーの展開の説明に従って、トポロジにスタンドアロンの仲介サーバー プールを既に定義して公開済みである必要があります。 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>スタンドアロンの仲介サーバー プールのファイルをインストールするには

1. インストール メディアで、アプリケーションを右クリック  _\<installation media\>_ **\Setup\amd64\Setup.exe、[** 管理者として実行] **をクリックします**。
    
2. [インストール場所 **] ページで****、[OK] をクリックします**。
    
3. [使用許諾契約 **書] ページで、[** 同意する] をクリックし **、[OK] をクリックします**。 (続行するには必須)。
    
4. **[Skype for Business Server 展開ウィザード] ページ** で **、[Skype for Business Server システムのインストールまたは更新] をクリックします**。
    
5. [手順 **1: ローカル構成ストア** のインストール] の横にある [実行] をクリックし、画面の指示に従います。
    
6. [中央 **管理ストアのローカル** レプリカの構成] ページで、既定の [中央管理ストアから直接取得] を受け入れ、[次へ] をクリック **します**。
    
7. [実行中 **のコマンド] ページ** で、タスクの状態が [完了] と表示されている場合 **は、[完了**] をクリック **します**。
    
8. [ステップ **2: Skype for Business Server** コンポーネントのセットアップまたは削除] の横にある [実行] をクリックし、[次へ] を **クリックします**。
    
9. [実行中 **のコマンド] ページ** で、タスクの状態が [完了] と表示されている場合 **は、[完了**] をクリック **します**。
    
10. [手順 **3: 証明書の要求、インストール、または割り** 当て] の横にある [実行] を **クリックします**。 画面の指示に従って、既定の設定を受け入れる。 仲介サーバーには 1 つの証明書が必要なので、手順 3 を **2** 回実行します。1 回は必要な証明書を発行し、もう 1 回は割り当てる必要があります。
    
11. 証明書が発行され、正しく割り当てられたら、[手順 **4:** サービスの開始] の横にある [実行] をクリックし、画面の指示に従います。
    
12. 手順 **4 が** 正常に完了したら、サーバーを再起動し、DomainAdmins グループのメンバーとしてサーバーにログオンします。
    
13. Skype for Business Server コントロール パネルを実行しているコンピューターで、Skype for Business Server コントロール パネルの [トポロジ] ページで、仲介サーバーのサービスの状態が緑色のチェック マークで表示されるのを確認します。  代わりに赤い X が表示される場合は、仲介サーバーを選択します。 [操作] **メニューの** [すべてのサービスの開始 **] をクリックします**。 
    
仲介サーバー プールに複数のコンピューターを追加した場合は、仲介サーバー プール内の他のすべてのコンピューターで、この手順の手順を実行します。 他のコンピューター用に仲介サーバー用のファイルをインストールする必要はない場合は [、「Skype for Business Server](configure-trunks.md) でトランクを構成する」の手順に従って、この仲介サーバー プール (またはサイト内のすべての仲介サーバー) とそのピア間のトランク接続の設定を構成します。

