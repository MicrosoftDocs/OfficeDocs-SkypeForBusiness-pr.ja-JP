---
title: 組織の SIP フェデレーション ドメインの管理
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フェデレーションできる SIP ドメインを管理し、構成する方法について説明します。
ms.openlocfilehash: 1a2f76f7f465401bae04b4defa2e0a1f5300ab0f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303971"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Skype for Business Server で組織の SIP フェデレーションドメインを管理する


フェデレーションできる SIP ドメインを管理して構成するには、次の操作を行います。

  - SIP フェデレーションパートナードメインの許可ドメインリストを作成または編集します。

  - SIP フェデレーションドメインのブロックドメインリストを作成または編集します。

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Skype for Business Server で許可されている外部ドメインのサポートを構成する

フェデレーションパートナーのサポートを構成している場合、組織とフェデレーションできる特定のドメインを管理することができます。 1つ以上の特定の外部ドメインを、許可されたフェデレーションドメインとして構成します。 そのためには、許可ドメインの一覧に各ドメインを追加します。 組織でパートナーの検出が有効になっている場合でも、ドメインが1000以上のユーザーと通信する必要がある、または1秒あたり20件を超えるメッセージを送信する必要があるフェデレーションパートナーである場合に、この操作を行います。 組織でパートナー検出が有効になっていない場合、許可されたドメインリストに追加した外部ドメインのユーザーのみが、組織内のユーザーと IM および会議に参加できます。 フェデレーションドメインへのアクセスをフェデレーションパートナーのアクセスエッジサービスを実行している特定のサーバーに制限する場合は、許可ドメインの一覧で、各ドメインのアクセスエッジサービスを実行しているサーバーのドメイン名を指定できます。

> [!NOTE]  
> この手順では、特定のドメインのサポートを構成する方法について説明します。フェデレーションユーザー向けのサポートを実装するには、組織のフェデレーションユーザーのサポートを有効にする必要があります。また、ポリシーを構成して適用して、ユーザーを管理することもできます。フェデレーションされたユーザーとの共同作業 フェデレーションユーザーのサポートを有効にする方法について詳しくは、「[リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」をご覧ください。 フェデレーションを制御するポリシーの構成の詳細については、「フェデレーションされた[ユーザーアクセスを制御するためのポリシーの構成](../external-access-policies/configure-policies-to-control-federated-user-access.md)」を参照してください。

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>許可ドメインの一覧に外部ドメインを追加するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**フェデレーションドメイン**] をクリックします。
4.  [**フェデレーションドメイン**] ページで、[**新規作成**] をクリックし、[許可した**ドメイン**] をクリックします。
5.  **新しいフェデレーションドメイン**で、次の操作を行います。
    
      - [ **Domain name (または FQDN)**] に、フェデレーションパートナードメインの名前を入力します。       

        > [!NOTE]  
        > この名前は一意であり、アクセスエッジサービスを実行しているこのサーバーで許可されているドメインとして既に存在することはできません。 名前の長さは、256文字以下にすることはできません。<BR><br>フェデレーションパートナーのドメイン名での検索では、サフィックス一致が実行されます。 たとえば、 **contoso.com**と入力すると、検索によってドメイン**it.contoso.com**も返されます。<BR><br>フェデレーションパートナードメインは、同時にブロックおよび許可することはできません。 Skype for Business Server では、リストを同期する必要がないように、この問題を回避することができます。
    
      - このフェデレーションドメインへのアクセスを、アクセスエッジサービス **(FQDN)** で実行されている特定のサーバーのユーザーに制限する場合は、アクセスエッジサービスを実行しているフェデレーションドメインのサーバーの FQDN を入力します。    
      - 追加情報を提供する場合は、[**コメント**] に、この構成について他のシステム管理者と共有する情報を入力します。

6.  [**コミット**] をクリックします。
7.  許可するフェデレーションパートナードメインごとに、手順 4 ~ 6 を繰り返します。

フェデレーションされたユーザーアクセスを有効にするには、組織でフェデレーションされたユーザーアクセスのサポートを有効にする必要もあります。 詳細について[は、「リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」を参照してください。

さらに、フェデレーションされたユーザーと共同作業できるようにするユーザーにポリシーを構成して適用する必要があります。 詳しくは、「フェデレーションされた[ユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-federated-user-access.md)」をご覧ください。

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Skype for Business Server でブロックされた外部ドメインのサポートを構成する 

フェデレーションパートナーのサポートを構成している場合は、どのドメインを組織とのフェデレーションからブロックするかを管理できます。 ブロックされたドメインの一覧はブロックリスト (許可されていない明示的なエントリの一覧) として機能し、このオプションを有効にしている場合はフェデレーションドメインの検出に適用されます。 詳細について[は、「フェデレーションパートナーの検出を有効または無効](../access-edge/enable-or-disable-discovery-of-federation-partners.md)にする」を参照してください。

1つ以上の外部ドメインをブロックして組織に接続します。 そのためには、ブロックされたドメインの一覧にドメインを追加します。


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>ブロックされたドメインの一覧に外部ドメインを追加するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 
3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックします。
4.  [**フェデレーションドメイン**] をクリックし、[**新規作成**] をクリックして、[**禁止ドメイン**] をクリックします。
5.  **新しいフェデレーションドメイン**で、次の操作を行います。
    
      - [ **Domain name (または FQDN)**] に、ブロックするフェデレーションパートナードメインの名前を入力します。

        > [!NOTE]  
        > 名前の長さは、256文字以下にすることはできません。<BR><br>フェデレーションパートナーのドメイン名での検索では、サフィックス一致が実行されます。 たとえば、 **contoso.com**と入力すると、検索によってドメイン**it.contoso.com**も返されます。<BR><br>フェデレーションパートナードメインは、同時にブロックおよび許可することはできません。 Skype for Business Server では、リストを同期する必要がないように、この問題を回避することができます。
   
      - 省略[**コメント**] に、この構成について他のシステム管理者と共有する情報を入力します。

6.  [**コミット**] をクリックします。
7.  ブロックするフェデレーションパートナーごとに、手順 4 ~ 6 を繰り返します。

フェデレーションされたユーザーアクセスを有効にするには、組織でフェデレーションされたユーザーアクセスのサポートを有効にする必要もあります。 詳細について[は、「リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」を参照してください。

さらに、フェデレーションされたユーザーと共同作業できるようにするユーザーにポリシーを構成して適用する必要があります。 詳しくは、「フェデレーションされた[ユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-federated-user-access.md)」をご覧ください。


## <a name="see-also"></a>関連項目

[フェデレーション ユーザー アクセスを制御するポリシーの構成](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[フェデレーションおよびパブリック IM 接続の有効化または無効化](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[フェデレーション パートナーの検出の有効化または無効化](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

