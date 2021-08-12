---
title: '[トポロジ] でトポロジを確認Skype for Business Server'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '概要: トポロジサーバーと Active Directory サーバー Skype for Business Server期待通り動作している状態を確認する方法について学習します。 以下の Microsoft 評価センター Skype for Business Server無料試用版をダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 743741fd18766116ed923a2af632f33c88343ef5957a84165edc7702b3b6593f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294774"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>[トポロジ] でトポロジを確認Skype for Business Server
 
**概要:** トポロジサーバーと Active Directory サーバー Skype for Business Server期待通り動作している状態を確認する方法について学習します。 Microsoft 評価センターからSkype for Business Server試用版[をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
トポロジが公開され、Skype for Business Server システム コンポーネントがトポロジ内の各サーバーにインストールされた後、トポロジが正常に動作している状態を確認する準備が整います。 これには、構成がすべての Active Directory サーバーに伝達され、ドメイン全体がドメイン内で使用可能Skype for Business確認できます。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示されている手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 トポロジの確認は、手順 8 / 8 です。
  
![概要図。](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>フロントエンド プールの展開をテストする

最後の手順は、フロントエンド プールをテストし、クライアントが相互に通信Skype for Business確認します。 
  
### <a name="add-users-and-verify-client-connectivity"></a>ユーザーの追加とクライアント接続の確認

1. Active Directory コンピューターとユーザーを使用して、Skype for Business Server 展開 (Skype for Business Server コントロール パネルがインストールされている) の管理者ロールの Active Directory ユーザー オブジェクトを **CSAdministrator** グループに追加します。
    
    > [!IMPORTANT]
    > CsAdministors グループに適切なユーザーとグループを追加しない場合は、Skype for Business Server コントロール パネルを開き、「承認されていない: 役割ベースのアクセス制御 (RBAC) 承認エラーが原因でアクセスが拒否されました」というエラーが表示されます。 
  
2. ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてから再度ログオンし、新しいグループ割り当てを登録します。
    
    > [!NOTE]
    > ユーザー アカウントは、ユーザー アカウントを実行しているサーバーのローカル管理者Skype for Business Server。 
  
3. 管理アカウントを使用して、コントロール パネルがインストールSkype for Business Serverコンピューターにログオンします。
    
4. コントロール Skype for Business Serverを開始し、プロンプトが表示されたら資格情報を入力します。 Skype for Business Serverコントロール パネルには、展開情報が表示されます。
    
5. 左側のナビゲーション バーで、[トポロジ] をクリックし、サービスの状態に緑色の矢印が付くコンピューターが表示され、展開およびオンライン化された各 Skype for Business Server 役割の横に、レプリケーション状態の緑色のチェック マークが表示されます。 
    
6. 左側のナビゲーション バーで、[**ユーザー**] をクリックし、[**ユーザーを有効にする**] をクリックします。 
    
7. [ユーザーの **新しいSkype for Business Server] ページで、[** 追加] を **クリックします**。
    
8. 検索するオブジェクトの検索パラメーターを定義するには、[**Active Directory から選択**] ページで [**検索**] を選択し、オプションで [**フィルターの追加**] をクリックできます。 また [**LDAP 検索**] を選択し、LDAP 表現を入力して、戻されるオブジェクトをフィルター処理または制限することもできます。 検索オプションを決定した後、[検索] を **クリックします**。
    
9. [検索結果] ウィンドウで、追加するユーザーを選択し **、[OK] をクリックします**。
    
10. [新 **しいユーザー Skype for Business Server] ページ** で、選択したユーザーが [ユーザー] 画面に **表示** されます。 [ユーザーを **プールに割り当てる] リスト** で、ユーザーが存在するサーバーを選択します。
    
    オブジェクトの構成に使用できるオプションの一覧を次に示します。
    
    - **ユーザーの SIP URI を生成する**
    
    - **テレフォニー**
    
    - [**回線 URI**]
    
    - **会議ポリシー**
    
    - **クライアント バージョン ポリシー**
    
    - **PIN ポリシー**
    
    - **外部アクセス ポリシー**
    
    - **アーカイブ ポリシー**
    
    - **場所のポリシー**
    
    - **クライアント ポリシー**
    
    基本的な機能をテストするには、ユーザーの **SIP URI** の生成設定に使用するオプション (構成の他のオプションでは既定の設定を使用)を選択し、図に示すように [有効] をクリックします。
    
     ![コントロール パネルでユーザーを有効にします。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. [有効] 列にチェック マークが表示され、ユーザーがセットアップ済みかどうかを示す概要ページが表示されます。 [SIP **アドレス]** 列には、ユーザー サインイン構成に必要なアドレスが表示されます。
    
     ![コントロール パネルにSkype for Business Serverユーザー。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. ドメインに参加しているコンピューターに 1 人のユーザーをログオンし、別のユーザーをドメイン内の別のコンピューターにログオンします。
    
13. 2 Skype for Business の各クライアント コンピューターにクライアントをインストールし、両方のユーザーが Skype for Business Server にサインインして、インスタント メッセージを互いに送信できると確認します。
    

