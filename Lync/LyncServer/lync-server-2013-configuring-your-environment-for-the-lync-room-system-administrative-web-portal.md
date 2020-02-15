---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルの環境の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c42b5541fb28646e4c01d9d070b67f6fe103234
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Lync Room System 管理 Web ポータル用に Lync Server 2013 環境を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-22_

Lync Room System (LRS) 管理 Web ポータルを使用するには、次の前提条件をインストールまたは構成する必要があります。

<div>


> [!IMPORTANT]  
> サーバーが Kerberos 認証と NTLM 認証の両方を使用して構成されており、ドメインに参加していないコンピューター上で LRS が実行されている場合、Kerberos 認証は失敗し、ユーザーには管理ポータルで LRS の状態が表示されません。 この問題を解決するには、サーバーを NTLM 認証または NTLM と DSK 認証 (Kerberos を使用しない) の両方で構成するか、または LRS コンピューターをドメインに参加させます。



</div>

1.  Lync server 2013 の累積的な更新プログラム (Lync Server トポロジでは2013年7月) をインストールします。
    
    更新プログラムを取得するか、またはその内容に含まれているものを確認するには、「 [Lync Server 2013 の更新プログラム](http://go.microsoft.com/fwlink/p/?linkid=323959)」を参照してください。

2.  SIP 対応の Active Directory ユーザーを作成します。
    
    LRS 管理 Web ポータルは、これらの資格情報を使用して Lync Server からの情報を照会します。 推奨されるユーザー名は LRSApp です。

3.  LRSSupportAdminGroup という名前の Active Directory セキュリティグループを作成します。
    
    グループスコープを持つグループを [グローバル] および [グループの種類] としてセキュリティとして作成します。 このグループに追加される SIP 対応ユーザーは、ルームのリストを確認し、ログの収集などの特定のコマンドを実行することを承認されます。

4.  LRSFullAccessAdminGroup という名前の Active Directory セキュリティグループを作成します。
    
    [グローバル] および [グループの種類] としてグループスコープを持つグループをセキュリティとして作成します。このグループに追加される SIP 対応ユーザーは、すべての管理ポータル機能を使用することを承認されています。
    
     
    
    ![セキュリティグループの役割を持つ管理グループの一覧](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "セキュリティグループの役割を持つ管理グループの一覧")  
    
     

5.  LRSFullAccessAdminGroup を LRSSupportAdminGroup のメンバーとして追加します。
    
    ![LRSSupportAdminGroup Properties メンバーページ](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties メンバーページ")  
    
     

6.  LRSSupport という名前の SIP 対応 Active Directory ユーザーを作成します。 このユーザーを LRSSupportAdminGroup に追加します。
    
    ![LRSSupportAdminGroup Properties メンバーページ](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties メンバーページ")  
    
     

7.  ASP.NET MVC 4 for Visual Studio 2010 SP1 および Visual Web Developer 2010 SP1 は、Microsoft ダウンロードセンター () から入手[http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)できます。

</div>

<span> </span>

</div>

</div>

</div>

