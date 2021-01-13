---
title: Skype for Business Server でのトポロジの確認
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
description: '概要: Skype for Business Server トポロジと Active Directory サーバーが期待通り動作を確認する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833837"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Skype for Business Server でのトポロジの確認
 
**概要:** Skype for Business Server トポロジと Active Directory サーバーが期待通り動作しているのを確認する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版 [をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
トポロジを公開し、トポロジ内の各サーバーに Skype for Business Server システム コンポーネントをインストールしたら、トポロジが期待通り動作している状態を確認できます。 これには、構成がすべての Active Directory サーバーに伝達され、ドメイン全体が Skype for Business がドメイン内で利用可能なことを知っていることを確認する機能が含まれます。 手順 1. ~ 5. は任意の順序で実行できます。 ただし、手順 6、7、および 8 を順番に実行し、図に示されている手順 1 ~ 5 の後に実行する必要があります。 トポロジの確認は手順 8/8 です。
  
![概要図](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>フロントエンド プールの展開をテストする

最後の手順では、フロントエンド プールをテストし、Skype for Business クライアントが相互に通信可能な環境を確認します。 
  
### <a name="add-users-and-verify-client-connectivity"></a>ユーザーの追加とクライアント接続の確認

1. Active Directory コンピューターとユーザーを使用して、(Skype for Business Server コントロール パネルがインストールされている) Skype for Business Server 展開の管理者の役割の Active Directory ユーザー オブジェクトを **CSAdministrator** グループに追加します。
    
    > [!IMPORTANT]
    > CsAdministors グループに適切なユーザーとグループを追加しない場合、Skype for Business Server コントロール パネルを開く際に、「Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.」というエラーが表示されます。 
  
2. ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてから再度ログオンし、新しいグループ割り当てを登録します。
    
    > [!NOTE]
    > ユーザー アカウントは、Skype for Business Server を実行しているサーバーのローカル管理者にすることはできません。 
  
3. 管理アカウントを使用して、Skype for Business Server コントロール パネルがインストールされているコンピューターにログオンします。
    
4. Skype for Business Server コントロール パネルを起動し、メッセージが表示されたら資格情報を入力します。 Skype for Business Server コントロール パネルには展開情報が表示されます。
    
5. 左側のナビゲーション バーで[トポロジ] をクリックし、サービスの状態に緑色の矢印が表示されたコンピューターと、展開されオンラインにされた各 Skype for Business Server の役割の横に、レプリケーション状態の緑色のチェック マークが表示されます。 
    
6. 左側のナビゲーション バーで、[**ユーザー**] をクリックし、[**ユーザーを有効にする**] をクリックします。 
    
7. [新しい **Skype for Business Server ユーザー] ページで、[** 追加] を **クリックします**。
    
8. 検索するオブジェクトの検索パラメーターを定義するには、[**Active Directory から選択**] ページで [**検索**] を選択し、オプションで [**フィルターの追加**] をクリックできます。 また [**LDAP 検索**] を選択し、LDAP 表現を入力して、戻されるオブジェクトをフィルター処理または制限することもできます。 検索オプションを決定した後、[検索] をクリック **します**。
    
9. [検索結果] ウィンドウで、追加するユーザーを選択し **、[OK]** をクリックします。
    
10. [ **新しい Skype for Business Server ユーザー] ページ** で、選択したユーザーが [ユーザー] 表示 **に表示** されます。 [ユーザー **をプールに割り当てる** ] ボックスの一覧で、ユーザーが存在するサーバーを選択します。
    
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
    
    基本的な機能をテストするには、[ユーザー **の SIP URI** を生成する] 設定に使用するオプションを選択し (構成内の他のオプションでは既定の設定を使用)、[有効] をクリックします (図を参照)。
    
     ![コントロール パネルでユーザーを有効にします。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. ユーザーがセットアップ中かどうかを示すチェック マークが **[有効** ] 列に表示される概要ページが表示されます。 **SIP アドレス列には**、ユーザーサインイン構成に必要なアドレスが表示されます。
    
     ![Skype for Business Server コントロール パネルに追加されたユーザー。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. ドメインに参加しているコンピューターに 1 人のユーザーをログオンし、別のユーザーをドメイン内の別のコンピューターにログオンします。
    
13. 2 台のクライアント コンピューターのそれぞれに Skype for Business クライアントをインストールし、両方のユーザーが Skype for Business Server にサインインして、インスタント メッセージを互いに送信できる点を確認します。
    

