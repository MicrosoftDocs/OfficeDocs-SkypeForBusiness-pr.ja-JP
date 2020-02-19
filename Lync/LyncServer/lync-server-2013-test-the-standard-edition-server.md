---
title: 'Lync Server 2013: Standard Edition サーバーのテスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26610b3619977413f3afa24027c7dfd757189a85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013 での Standard Edition サーバーのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

次の手順では、Standard Edition サーバーの展開をテストする方法について説明します。

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>Standard Edition サーバーの展開をテストするには

1.  [Active Directory コンピューターとユーザー] を使用して、Lync Server 2013 展開 (Lync Server コントロールパネルがインストールされている) の管理者ロールの Active Directory ユーザーオブジェクトを**Csadministrator**グループに追加します。

2.  ユーザー オブジェクトが現在ログオンしている場合は、ログオフしてから再度ログオンし、新しいグループ割り当てを登録します。
    
    <div>
    

    > [!NOTE]  
    > ユーザーアカウントは、Lync Server 2013 Standard Edition を実行しているサーバーのローカル管理者になることはできません。 CsAdministors グループに適切なユーザーとグループを追加しないと、Lync Server 2013 コントロールパネルを開くときに、"権限のない: 役割ベースのアクセス制御 (RBAC) の承認エラーによりアクセスが拒否されました" というエラーが表示されます。

    
    </div>

3.  管理者アカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。

4.  メッセージが表示されたら、Lync Server コントロールパネルを起動し、資格情報を入力します。 Lync Server 2013 コントロールパネルに展開情報が表示されます。

5.  左側のナビゲーションバーで [**トポロジ**] をクリックし、サービスの状態が緑色の矢印が表示されているコンピューターのアイコンになっており、展開済みでオンラインになっている各 Lync server サーバーの役割の横に緑のチェックマークが表示されていることを確認します。

6.  左側のナビゲーションバーで [**ユーザー**] をクリックし、Lync Server 2013 の2人のユーザーを有効にします。

7.  1 人のユーザーがドメインに参加しているコンピューターにログオンし、もう 1 人のユーザーがドメイン内の別のコンピューターにログオンします。

8.  2台の各クライアントコンピューターに Lync Server 2013 をインストールしてから、両方のユーザーが Lync Server 2013 にサインインして、互いにインスタントメッセージを送信できることを確認します。

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

