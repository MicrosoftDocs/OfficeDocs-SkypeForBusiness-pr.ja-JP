---
title: 'Lync Server 2013: 公開 SIP フェデレーション プロバイダーの作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876a79e840990afb0c9cf0bae4fc819ec10db5d8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

パブリックインスタントメッセージング (IM) 接続を使うと、組織内のユーザーは IM を使用して、Windows Live Messenger、Yahoo\!、AOL など、パブリック im サービスプロバイダーが提供する im サービスのユーザーと通信できます。

Lync Server 2013 には、America Online、Windows Live、Yahoo 用のパブリックプロバイダー構成があります。\! インスタントメッセージ (im)。 各パブリックプロバイダーは、プロバイダーのエッジサーバーの完全修飾ドメイン名で構成され、既定の認証レベルでは、**このプロバイダーを使用する連絡先リストのユーザーのみとの通信を許可**します。

既定の設定では、どのパブリックプロバイダーも有効になっていません。 パブリックプロバイダーを有効にする前に、ライセンス契約とプロビジョニング作業を完了する必要があります。 ライセンスとプロビジョニングの作業を完了する前に、プロバイダーを有効にすることができます。 ユーザーは、前提条件となる作業が完了するまで、これらのプロバイダーの連絡先と通信できません。 パブリックプロバイダーのライセンスとプロビジョニングの詳細については、「 [Lync Server 2013 でパブリックユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-public-user-access.md)」を参照してください。

パブリックプロバイダーを作成または編集するには、次の手順を使用します。

<div>

## <a name="to-create-or-edit-public-providers"></a>パブリックプロバイダーを作成または編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[ **SIP フェデレーションプロバイダー**] をクリックします。

4.  新しいパブリックプロバイダーを作成する必要がある場合は、[**新規**] をクリックし、[**パブリックプロバイダー**] をクリックします。

5.  パブリックプロバイダーの一覧からエントリを編集する必要がある場合は、パブリックプロバイダーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

6.  [ **SIP フェデレーションプロバイダーの編集**] ページでは、次の設定を入力または編集できます。
    
      - **このプロバイダー**   との通信を有効にするこの設定をオンにすると、このプロバイダーのユーザーとの IM が有効になります。
    
      - **[Provider name]:**   必要なプロパティは、SIP フェデレーションプロバイダーの一覧に反映されるプロバイダーの名前を入力します。
    
      - **Access edge サービス (FQDN):**   必要なプロパティで、構成しているプロバイダーのアクセスエッジサービスの完全修飾ドメイン名を入力します。 この情報は既定の項目として提供され、パブリックプロバイダーがアクセスエッジサービスの FQDN に変更を加えた場合にのみ変更する必要があります。
    
      - **既定の確認レベル:**   既定の設定では、ユーザーが連絡先リストに登録されているユーザー**との通信を許可**します。このプロバイダーを使用すると、承諾した連絡先と連絡先リストに含まれている連絡先への通信が制限されます。
        
        [**このプロバイダーを使用するすべてのユーザーとの通信を許可する**] を選択すると、連絡先への招待を受信して受け付けるために必要な制限が解除されます。 この設定では、パブリックプロバイダーのネットワークから連絡できるユーザーを制限することはできません。

7.  設定の構成が完了したら、[**確定**] をクリックするか、[**キャンセル**] をクリックして変更を破棄します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

