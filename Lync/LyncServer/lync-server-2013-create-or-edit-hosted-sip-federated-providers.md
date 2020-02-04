---
title: 'Lync Server 2013: ホスト SIP フェデレーション プロバイダーの作成または編集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6c97255ce1dc9fce00d9eca6f358f4c68e1ff8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

ホストされているプロバイダーのインスタントメッセージング (IM) 接続により、組織内のユーザーは、Microsoft Office 365 と Lync Online を含む、ホスティングプロバイダーによって提供される IM サービスのユーザーとの通信に IM を使用できるようになります。

ホストされる各プロバイダーは、プロバイダーのエッジサーバーの完全修飾ドメイン名で構成され、既定の認証レベルでは、**このプロバイダーを使用する連絡先リストのユーザーのみとの通信を許可**します。

ホストされるプロバイダーを作成または編集するには、次の手順を使用します。

<div>

## <a name="to-create-or-edit-hosted-providers"></a>ホストされているプロバイダーを作成または編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**フェデレーションと外部アクセス**] をクリックし、[ **SIP フェデレーションプロバイダー**] をクリックします。

4.  新しいホスティングプロバイダーを作成する必要がある場合は、[**新規**] をクリックし、[ホストされる**プロバイダー**] をクリックします。

5.  ホストされているプロバイダーの一覧からエントリを編集する必要がある場合は、ホストされているプロバイダーを選択し、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

6.  [ **SIP フェデレーションプロバイダーの編集**] ページでは、次の設定を入力または編集できます。
    
      - **このプロバイダー**   との通信を有効にするこの設定をオンにすると、このプロバイダーのユーザーとの通信が有効になります。
    
      - **[Provider name]:**   必要なプロパティは、SIP フェデレーションプロバイダーの一覧に反映されるプロバイダーの名前を入力します。
    
      - **Access edge サービス (FQDN):**   必須プロパティ。構成するホストされているプロバイダーのアクセスエッジサービスの完全修飾ドメイン名を入力します。 この情報は、ホストされたプロバイダーによって提供される必要があります。また、ホストされているプロバイダーが、ホストされているプロバイダーでアクセスエッジサービスの FQDN に変更を加えた場合にのみ変更する必要があります。
    
      - **既定の確認レベル:**   既定の設定では、ユーザーが連絡先リストに登録されているユーザー**との通信を許可**します。このプロバイダーを使用すると、承諾した連絡先と連絡先リストに含まれている連絡先への通信が制限されます。
        
        [**このプロバイダーを使用するすべてのユーザーとの通信を許可する**] を選択すると、連絡先への招待を受信して受け付けるために必要な制限が解除されます。 この設定では、ホストされているプロバイダーのネットワークから連絡できるユーザーを制限することはできません。

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

