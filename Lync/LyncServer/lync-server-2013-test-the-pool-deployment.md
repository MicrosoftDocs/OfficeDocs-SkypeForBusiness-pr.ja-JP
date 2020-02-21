---
title: 'Lync Server 2013: プール展開のテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 552677dde2706265093879bc9b48ac803e1365fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Lync Server 2013 でプール展開をテストする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-09-25_

次の手順では、フロントエンドプールの展開をテストする方法について説明します。

<div>

## <a name="to-test-the-pool-deployment"></a>プール展開をテストするには

1.  Active Directory のコンピューターとユーザーを使用して、Lync Server 2013 の展開 (Lync Server 2013 コントロールパネルがインストールされている) の管理者ロールの Active Directory ユーザーオブジェクトを**Csadministrator**グループに追加します。
    
    <div>
    

    > [!IMPORTANT]  
    > CsAdministors グループに適切なユーザーとグループを追加しないと、Lync Server コントロールパネルを開くときにエラーが表示されます。これは、"権限のない: 役割ベースのアクセス制御 (RBAC) の承認エラーによってアクセスが拒否されました" というメッセージを表示します。

    
    </div>

2.  ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてから再度ログオンし、新しいグループ割り当てを登録します。
    
    <div>
    

    > [!NOTE]  
    > ユーザーアカウントは、Lync Server 2013 を実行しているサーバーのローカル管理者になることはできません。

    
    </div>

3.  管理者アカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。

4.  [Lync Server コントロールパネル] を起動し、メッセージが表示された場合は、資格情報を入力します。 Lync Server コントロールパネルに展開情報が表示されます。

5.  左側のナビゲーションバーで [**トポロジ**] をクリックし、サービスの状態に緑色の矢印が表示されていること、および展開されてオンラインになっている各 Lync server のサーバーの役割の横に、レプリケーションの状態を示す緑のチェックマークが付いていることを確認します。

6.  左側のナビゲーション バーで、[**ユーザー**] をクリックし、[**ユーザーを有効にする**] をクリックします。

7.  [**新規 Lync Server ユーザー**] ページで [**追加**] をクリックします。

8.  検索するオブジェクトの検索パラメーターを定義するには、[**Active Directory から選択**] ページで [**検索**] を選択し、オプションで [**フィルターの追加**] をクリックできます。 また [**LDAP 検索**] を選択し、LDAP 表現を入力して、戻されるオブジェクトをフィルター処理または制限することもできます。 [検索] オプションの内容を決定した後、[**検索**] をクリックします。

9.  [検索結果] ウィンドウでこの検索セッションのオブジェクトをすべて選択し、[**OK**] をクリックします。

10. [**新しい Lync Server ユーザー**] ページで、選択した 1 つまたは複数のオブジェクトが [**ユーザー**] に表示されます。 [**ユーザーのプールへの割り当て**] リストで、オブジェクトの所属先となるサーバーを選択します。
    
    オブジェクトを構成するためのいくつかのオプションを次に示します。
    
      - **ユーザーの SIP URI の生成**
    
      - **網**
    
      - [**回線 URI**]
    
      - **会議ポリシー**
    
      - **クライアント バージョン ポリシー**
    
      - **PIN ポリシー**
    
      - **外部アクセス ポリシー**
    
      - **アーカイブ ポリシー**
    
      - **場所のポリシー**
    
      - **クライアント ポリシー**
    
    基本機能をテストするには、[**ユーザーの SIP URI の生成**] 設定の任意のオプションを選択し (構成内のその他のオプションでは既定の設定を使用)、[**有効にする**] をクリックします。

11. 概要ページが表示されます。このページの [**有効にする**] の列に、オブジェクトが使用できることを示すチェック マークが表示されます。 [**SIP アドレス**] の列に、ユーザーのサインインの構成に必要なアドレスが表示されます。

12. あるユーザーはドメインに参加しているコンピューターにログオンし、他のユーザーはドメイン内の他のコンピューターにログオンします。

13. 2台の各クライアントコンピューターに Lync 2013 をインストールしてから、両方のユーザーが Lync Server 2013 にサインインして、互いにインスタントメッセージを送信できることを確認します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

