---
title: Skype for Business Serverでトポロジを確認する
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '概要: Skype for Business Server トポロジと Active Directory サーバーが想定どおりに動作していることを確認する方法について説明します。'
ms.openlocfilehash: ec63977f4c70845f39aafe3521591ec93777f7d5
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860548"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Skype for Business Serverでトポロジを確認する
 
**概要：** Skype for Business Server トポロジと Active Directory サーバーが想定どおりに動作していることを確認する方法について説明します。
  
トポロジが公開され、トポロジ内の各サーバーにインストールされたSkype for Business Server システム コンポーネントが完了したら、トポロジが期待どおりに動作していることを確認できます。 これには、ドメイン全体がドメイン内で使用可能であることをドメイン全体で認識できるように、構成がすべての Active Directory サーバーに伝達されたことを確認するSkype for Business含まれます。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示すように、手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 トポロジの確認は、手順 8/ 8 です。
  
![概要図。](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>フロントエンド プールのデプロイをテストする

最後の手順では、フロントエンド プールをテストし、Skype for Business クライアントが相互に通信できることを確認します。 
  
### <a name="add-users-and-verify-client-connectivity"></a>ユーザーを追加し、クライアント接続を確認する

1. Active Directory コンピューターとユーザーを使用して、Skype for Business Server展開 (Skype for Business Server コントロール パネルがインストールされている) の管理者ロールの Active Directory ユーザー オブジェクトを **CSAdministrator** グループに追加します。
    
    > [!IMPORTANT]
    > CsAdministors グループに適切なユーザーとグループを追加しないと、"承認されていない: ロールベースのアクセス制御 (RBAC) 承認エラーが原因でアクセスが拒否されました" というSkype for Business Server コントロール パネルを開くと、エラーが表示されます。 
  
2. ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてから再度ログオンし、新しいグループ割り当てを登録します。
    
    > [!NOTE]
    > ユーザー アカウントは、Skype for Business Serverを実行しているサーバーのローカル管理者にすることはできません。 
  
3. 管理アカウントを使用して、Skype for Business Server コントロール パネルがインストールされているコンピューターにログオンします。
    
4. Skype for Business Server コントロール パネルを開始し、プロンプトが表示されたら資格情報を入力します。 Skype for Business Server コントロール パネル展開情報が表示されます。
    
5. 左側のナビゲーション バーで [**トポロジ**] をクリックし、サービスの状態に緑色の矢印が付いたコンピューターが表示され、デプロイされてオンラインになった各Skype for Business Server ロールの横にレプリケーション状態の緑色のチェック マークが表示されていることを確認します。 
    
6. 左側のナビゲーション バーで、[**ユーザー**] をクリックし、[**ユーザーを有効にする**] をクリックします。 
    
7. [**新しいSkype for Business Server ユーザー**] ページで、[**追加**] をクリックします。
    
8. 検索するオブジェクトの検索パラメーターを定義するには、[**Active Directory から選択**] ページで [**検索**] を選択し、オプションで [**フィルターの追加**] をクリックできます。 また [**LDAP 検索**] を選択し、LDAP 表現を入力して、戻されるオブジェクトをフィルター処理または制限することもできます。 検索オプションを決定したら、[ **検索**] をクリックします。
    
9. [検索結果] ウィンドウで、追加するユーザーを選択し、[OK] をクリック **します**。
    
10. [**新しいSkype for Business Server ユーザー]** ページで、選択したユーザーが [**ユーザー]** 画面に表示されます。 [ **プールにユーザーを割り当てる** ] ボックスの一覧で、ユーザーが存在するサーバーを選択します。
    
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
    
    基本的な機能をテストするには、[ **ユーザーの SIP URI の生成** ] 設定に必要なオプション (構成の他のオプションでは既定の設定を使用) を選択し、図に示すように **[有効]** をクリックします。
    
     ![コントロール パネルでユーザーを有効にします。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. [ **有効]** 列にユーザーが設定されていることを示すチェック マークを示す概要ページが表示されます。 **[SIP アドレス]** 列には、ユーザー サインイン構成に必要なアドレスが表示されます。
    
     ![Skype for Business Server コントロール パネルに追加されたユーザー。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. ドメインに参加しているコンピューターに 1 人のユーザーをログオンし、別のユーザーをドメイン内の別のコンピューターにログオンします。
    
13. Skype for Businessクライアントを 2 台のクライアント コンピューターにインストールし、両方のユーザーがSkype for Business Serverにサインインでき、インスタント メッセージを相互に送信できることを確認します。
    

