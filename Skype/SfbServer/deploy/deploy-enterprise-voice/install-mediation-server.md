---
title: Skype for Business Server に仲介サーバー用のファイルをインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: '概要: Skype for Business Server に仲介サーバー用のファイルをインストールする方法について説明します。'
ms.openlocfilehash: b73832586ba4a09cc51f67bddcaf30c2f85fcca1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240298"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Skype for Business Server に仲介サーバー用のファイルをインストールする
 
**概要:** Skype for Business Server に仲介サーバー用のファイルをインストールする方法について説明します。
  
この手順を正常に完了するには、少なくともローカルの管理者または RTCUniversalReadOnlyAdmins グループのメンバーシップを持つドメイン ユーザーとして、サーバーにログオンしている必要があります。
  
このトピックの手順を使用して、Skype for Business Server Deployment ウィザードを実行し、[トポロジビルダー] を使用してプールを定義して発行した後に、仲介サーバープールに追加したコンピューターに仲介サーバー用のファイルをインストールします。 ファイル仲介サーバーをインストールする場合は、仲介サーバープール内の各コンピューターに必要な証明書もインストールして割り当てます。 
  
> [!NOTE]
> このトピックでは、「 [Skype For Business server のトポロジビルダーで仲介サーバーを展開](deploy-a-mediation-server.md)する」に記載されているように、既に自分のトポロジにスタンドアロンの仲介サーバープールを定義して公開していることを前提としています。 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>スタンドアロンの仲介サーバー プールにファイルをインストールするには

1. インストールメディアから [ _ \<インストール\>メディア_ **\Setup\amd64\Setup.exe**] を右クリックし、[**管理者として実行**] をクリックします。
    
2. [**インストール先**] ページで、[**OK**] をクリックします。
    
3. [**使用許諾契約書**] ページで [**同意する**] をクリックし、[**OK**] をクリックします (操作を続行する必要があります)。
    
4. Skype for **Business Server 展開ウィザード**のページで、[ **Skype For business Server システムのインストールまたは更新**] をクリックします。
    
5. [**ステップ 1: ローカル構成ストアのインストール**] の横の [**実行**] をクリックし、画面の指示に従います。
    
6. [**中央管理ストアのローカル レプリカの構成**] ページで、既定の [**中央管理ストアから直接取得する**] を受け入れ、[**次へ**] をクリックします。
    
7. [**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。
    
8. **「手順 2: Skype For Business Server コンポーネントのセットアップまたは削除**」の横にある [**実行**] をクリックし、[**次へ**] をクリックします。
    
9. [**コマンドの実行**] ページで、タスクの状態が [**完了**] と表示されたら、[**完了**] をクリックします。
    
10. [**ステップ 3: 証明書の要求、インストール、または割り当て**] の横にある [**実行**] をクリックします。画面に表示される指示に従って、既定の設定を承諾します。仲介サーバーには証明書が 1 つ必要なため、[**ステップ 3**] を 2 回実行します。つまり、1 回目で必要な証明書を発行して、2 回目で割り当てを行います。
    
11. 証明書を発行し正しく割り当てたら、[**ステップ 4: サービスの開始**] の横の [**実行**] をクリックし、画面の指示に従います。
    
12. [**ステップ 4**] が正常に完了したら、サーバーを再起動し、DomainAdmins グループのメンバーとしてサーバーにログオンします。
    
13. Skype for business Server コントロールパネルを実行しているコンピューターで、仲介サーバーのサービスの状態が緑色のチェックマークとして表示される、[Skype for Business Server] コントロールパネルの [**トポロジ**] ページを確認します。 代わりに赤い X が表示される場合は、仲介サーバーを選びます。 [**操作**] メニューの [**すべてのサービスを開始**] をクリックします。 
    
複数のコンピューターを仲介サーバープールに追加した場合は、仲介サーバープール内の他のすべてのコンピューターで、この手順の手順を実行します。 他のコンピューターに対して、仲介サーバー用のファイルをインストールする必要がない場合は、「 [Skype For Business Server で trunks を構成](configure-trunks.md)する」の手順に従って、この仲介サーバープールの間のトランク接続の設定を構成します (またはすべての仲介サイト内のサーバー) とそのピア。

