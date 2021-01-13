---
title: 組織の SIP フェデレーション ドメインの管理
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: フェデレーションを行える SIP ドメインを管理および構成する方法について学習します。
ms.openlocfilehash: 7b04225542387d52a36533c9639b02f773731e9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817217"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Skype for Business Server で組織の SIP フェデレーション ドメインを管理する


フェデレーションを行うことができる SIP ドメインを管理および構成する場合、次の操作を実行できます。

  - SIP フェデレーション パートナー ドメインの許可されたドメイン リストを作成または編集する

  - SIP フェデレーション ドメインの禁止ドメイン リストを作成または編集する

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Skype for Business Server で許可された外部ドメインのサポートを構成する

フェデレーション パートナーのサポートを構成している場合は、組織とフェデレーションできる特定のドメインを管理できます。 1 つ以上の特定の外部ドメインを許可されたフェデレーション ドメインとして構成します。 これを行うには、許可されたドメインの一覧に各ドメインを追加します。 組織でパートナー検出が有効になっている場合でも、ドメインが 1,000 を超えるユーザーと通信する必要があるフェデレーション パートナーである場合や、1 秒あたり 20 件を超えるメッセージを送信する必要がある場合は、この操作を行います。 組織でパートナーの検出が有効になっていない場合、許可されたドメインの一覧に追加した外部ドメインのユーザーだけが、組織内のユーザーとの IM および会議に参加できます。 フェデレーション ドメインのアクセスを、フェデレーション パートナーのアクセス エッジ サービスを実行している特定のサーバーに制限する場合は、許可されたドメインの一覧で、各ドメインのアクセス エッジ サービスを実行しているサーバーのドメイン名を指定できます。

> [!NOTE]  
> この手順では、特定のドメインのサポートを構成する方法について説明しますが、フェデレーション ユーザーのサポートを実装するには、組織のフェデレーション ユーザーのサポートを有効にし、フェデレーション ユーザーと共同作業できるユーザーを制御するポリシーを構成および適用する必要があります。 フェデレーション ユーザーのサポートを有効にする方法の詳細については、「リモート ユーザー アクセスを有効または無効にする」 [を参照してください](../access-edge/enable-or-disable-remote-user-access.md)。 フェデレーションを制御するポリシーの構成の詳細については、「フェデレーション ユーザー アクセスを制御するポリシーを構成 [する」を参照してください](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>許可されたドメインの一覧に外部ドメインを追加するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2.  ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
3.  左側のナビゲーション バーで、[外部ユーザー アクセス **] を** クリックし、[フェデレーション ドメイン] **をクリックします**。
4.  [フェデレーション **ドメイン] ページで、[** 新規] **をクリックし**、[許可されたドメイン] **をクリックします**。
5.  [**新規フェデレーション ドメイン**] で、次の操作を実行します。
    
      - [ **ドメイン名 ( FQDN) ]** に、フェデレーション パートナー ドメインの名前を入力します。       

        > [!NOTE]  
        > この名前は一意である必要があります。また、アクセス エッジ サービスを実行しているこのサーバーの許可ドメインとして存在することはできません。 名前の長さは、最大 256 文字です。<BR><br>フェデレーション パートナー ドメインの名前についての検索では、サフィックスの一致が実行されます。たとえば、**contoso.com** と入力すると、検索によりドメイン **it.contoso.com** も戻されます。<BR><br>フェデレーション パートナー ドメインを同時に禁止および許可することはできません。 Skype for Business Server では、この問題が発生しないので、リストを同期する必要はありません。
    
      - このフェデレーション ドメインのアクセスを、アクセス エッジ サービスを実行している特定のサーバーのユーザーに制限する場合は、アクセス エッジ サービス **(FQDN)** で、アクセス エッジ サービスを実行しているフェデレーション ドメインのサーバーの FQDN を入力します。    
      - 追加情報を提供する場合は **、Comment** に、この構成に関して他のシステム管理者と共有する情報を入力します。

6.  [**確定**] をクリックします。
7.  許可するフェデレーション パートナー ドメインごとに、手順 4. ~ 6. を繰り返します。

フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーション ユーザー アクセスのサポートも有効にする必要があります。 詳細については、「リモート ユーザー [アクセスを有効または無効にする」を参照してください](../access-edge/enable-or-disable-remote-user-access.md)。

また、ポリシーを構成して、フェデレーション ユーザーと共同作業できるようにするユーザーに適用する必要があります。 詳細については、「フェデレーション ユーザー [アクセスを制御するポリシーを構成する」を参照してください](../external-access-policies/configure-policies-to-control-federated-user-access.md)。

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Skype for Business Server でブロックされた外部ドメインのサポートを構成する 

フェデレーション パートナーに対するサポートが構成されている場合、組織とのフェデレーションを禁止するドメインを管理できます。 このオプションが有効な場合は、禁止されているドメインの一覧は禁止リスト (許可されていない明示的なエントリの一覧) として機能し、フェデレーション ドメインの検出時に適用されます。 詳細については、「フェデレーション パートナー [の検出を有効または無効にする」を参照してください](../access-edge/enable-or-disable-discovery-of-federation-partners.md)。

1 つまたは複数の外部ドメインの組織への接続を禁止します。この構成を実行するには、ドメインを禁止ドメインの一覧に追加します。


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>外部ドメインを禁止ドメインの一覧に追加するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2.  ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックします。
4.  [**フェデレーション ドメイン**] をクリックし、[**新規**] をクリックし、[**禁止ドメイン**] をクリックします。
5.  [**新規フェデレーション ドメイン**] で、次の操作を実行します。
    
      - [**ドメイン名 (または FQDN)**] で、禁止するフェデレーション パートナー ドメインの名前を入力します。

        > [!NOTE]  
        > 名前の長さは、最大 256 文字です。<BR><br>フェデレーション パートナー ドメインの名前についての検索では、サフィックスの一致が実行されます。たとえば、**contoso.com** と入力すると、検索によりドメイン **it.contoso.com** も戻されます。<BR><br>フェデレーション パートナー ドメインを同時に禁止および許可することはできません。 Skype for Business Server では、この問題が発生しないので、リストを同期する必要はありません。
   
      - (オプション) [**コメント**] で、この構成について他のシステム管理者と共有する必要のある情報を入力します。

6.  [**確定**] をクリックします。
7.  禁止するフェデレーション パートナーごとに、ステップ 4 ～ 6 を繰り返します。

フェデレーション ユーザー アクセスを有効にするには、組織でフェデレーション ユーザー アクセスのサポートも有効にする必要があります。 詳細については、「リモート ユーザー [アクセスを有効または無効にする」を参照してください](../access-edge/enable-or-disable-remote-user-access.md)。

また、ポリシーを構成して、フェデレーション ユーザーと共同作業できるようにするユーザーに適用する必要があります。 詳細については、「フェデレーション ユーザー [アクセスを制御するポリシーを構成する」を参照してください](../external-access-policies/configure-policies-to-control-federated-user-access.md)。


## <a name="see-also"></a>関連項目

[フェデレーション ユーザー アクセスを制御するポリシーの構成](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[フェデレーションおよびパブリック IM 接続の有効化または無効化](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[フェデレーション パートナーの検出の有効化または無効化](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

