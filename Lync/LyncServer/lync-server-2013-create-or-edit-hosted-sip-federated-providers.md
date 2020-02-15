---
title: 'Lync Server 2013: ホストされた SIP フェデレーションプロバイダーの作成または編集'
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
ms.openlocfilehash: 68e87e5a6a59c2e14705d8a89578a0408c39b8e6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>ホスト SIP フェデレーションプロバイダー Lync Server 2013 を作成または編集する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

ホストされるプロバイダーのインスタントメッセージング (IM) 接続により、組織内のユーザーは IM を使用して、ホストされたプロバイダーが提供する IM サービス (Microsoft Office 365 と Lync Online など) のユーザーと通信できるようになります。

各ホストされるプロバイダーは、プロバイダーのエッジ サーバーの完全修飾ドメイン名と、既定の確認レベルである [**連絡先リストのユーザーのうち、このプロバイダーを使うユーザーとの通信のみを許可する**] によって構成されます。

ホストされるプロバイダーを作成または編集するには、次の手順を使用します。

<div>

## <a name="to-create-or-edit-hosted-providers"></a>ホストされるプロバイダーを作成または編集するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**SIP フェデレーション プロバイダー**] をクリックします。

4.  新しいホストされるプロバイダーを作成するには、[**新規**] をクリックし、[**ホストされるプロバイダー**] をクリックします。

5.  ホストされるプロバイダーの一覧に示されるプロバイダーを編集する必要がある場合は、編集するプロバイダーを選択し、[**編集**]、[**編集の表示**] の順にクリックします。

6.  [**編集 SIP フェデレーション プロバイダー**] ページで、次の設定を入力または編集できます。
    
      - **[このプロバイダー**   との通信を有効にする] この設定を選択すると、このプロバイダーのユーザーとの通信が有効になります。
    
      - **プロバイダー名:**   必要なプロパティ。プロバイダーの名前を入力します。これは、SIP フェデレーションプロバイダーの一覧に反映されます。
    
      - **アクセスエッジサービス (FQDN):**   必要なプロパティ。構成するホストされるプロバイダーのアクセスエッジサービスの完全修飾ドメイン名を入力します。 この情報は、ホストされているプロバイダーによって提供される必要があります。ホストされているプロバイダーがアクセスエッジサービスの FQDN に変更を加える場合にのみ変更する必要があります。
    
      - **既定の検証レベル:**   既定の設定では、**このプロバイダーを使用するユーザーが連絡先リストにあるユーザーとの通信を許可**します。このプロバイダーを使用すると、承諾した連絡先リストに含まれる連絡先への通信が制限されます。
        
        [**このプロバイダーを使うすべてのユーザーとの通信を許可する**] を選択すると、連絡先に対する制限が削除されます。この設定は、ホストされるプロバイダーのネットワークからの通信を制限しません。

7.  設定の構成が終了したら、[**コミット**] をクリックして保存するか、[**キャンセル**] をクリックして変更を破棄します。

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

