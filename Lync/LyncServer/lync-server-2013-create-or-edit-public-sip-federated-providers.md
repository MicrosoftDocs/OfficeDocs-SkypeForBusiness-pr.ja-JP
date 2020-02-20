---
title: 'Lync Server 2013: パブリック SIP フェデレーションプロバイダーの作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51e31c731270bc0e3e25da712db5aff9137d84b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

パブリックインスタントメッセージング (IM) 接続を使用すると、組織内のユーザーは IM を使用して、パブリック IM サービスプロバイダーが提供する IM サービス (Windows Live Messenger\!、YAHOO、AOL など) のユーザーと通信することができます。

Lync Server 2013 には、America Online、Windows Live、Yahoo 用のパブリックプロバイダー構成があります。\! の各インスタント メッセージングのパブリック プロバイダー構成が含まれています。 各パブリック プロバイダーは、そのプロバイダーのエッジ サーバーの完全修飾ドメイン名と、既定の確認レベルである [**Allow users to communicate only with people on their Contacts list who use this provider**] を指定して構成されています。

既定の設定では、パブリック プロバイダーはいずれも無効になっています。 パブリック プロバイダーを有効にする前に、使用許諾契約とプロビジョニング作業を完了する必要があります。 ライセンスとプロビジョニングの作業を完了する前にプロバイダーを有効にできます。 前提条件となる作業を完了するまで、ユーザーはそのプロバイダーで連絡先と通信することはできません。 パブリックプロバイダーのライセンスとプロビジョニングの詳細については、「 [Configure policies to control public user access In Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)」を参照してください。

次の手順を使用して、パブリック プロバイダーを作成または編集します。

<div>

## <a name="to-create-or-edit-public-providers"></a>パブリック プロバイダーを作成または編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**フェデレーションと外部アクセス**] をクリックし、[**SIP フェデレーション プロバイダー**] をクリックします。

4.  新しいパブリック プロバイダーを作成する必要がある場合は、[**新規作成**] をクリックし、[**パブリック プロバイダー**] をクリックします。

5.  パブリック プロバイダーの一覧のエントリを編集する必要がある場合は、パブリック プロバイダーを選択し、[**編集**] をクリックして [**詳細の表示**] をクリックします。

6.  [**編集 SIP フェデレーション プロバイダー**] ページでは、次の設定を入力または編集できます。
    
      - **[このプロバイダー**   との通信を有効にする] この設定を選択すると、このプロバイダーのユーザーとの IM が有効になります。
    
      - **プロバイダー名:**   必要なプロパティ。プロバイダーの名前を入力します。これは、SIP フェデレーションプロバイダーの一覧に反映されます。
    
      - **アクセスエッジサービス (FQDN):**   必要なプロパティ。構成するプロバイダーのアクセスエッジサービスの完全修飾ドメイン名を入力します。 この情報は既定のアイテムとして提供され、パブリックプロバイダがパブリックプロバイダのアクセスエッジサービスの FQDN に変更を加える場合にのみ変更する必要があります。
    
      - **既定の検証レベル:**   既定の設定では、**このプロバイダーを使用するユーザーが連絡先リストにあるユーザーとの通信を許可**します。このプロバイダーを使用すると、承諾した連絡先リストに含まれる連絡先への通信が制限されます。
        
        [**Allow users to communicate with everyone using this provider**] を選択すると、連絡先からの招待を受け取って承認しておく必要があるという制限がなくなります。この設定では、パブリック プロバイダーのネットワークからユーザーに連絡できる相手先は制限されません。

7.  設定の構成が完了したら、[**コミット**] をクリックして保存するか、[**キャンセル**] をクリックして変更を破棄します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

