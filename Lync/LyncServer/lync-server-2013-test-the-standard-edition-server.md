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
ms.openlocfilehash: 00918643fcc59efc33d12dc3f8f77c7d3ac69815
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013 での Standard Edition サーバーのテスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

次の手順では、Standard Edition サーバーの展開をテストする方法について説明します。

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>Standard Edition サーバーの展開をテストするには

1.  Active Directory コンピューターとユーザーを使用して、Lync Server 2013 展開用の管理者ロールの Active Directory ユーザーオブジェクト (Lync Server コントロールパネルがインストールされている場合) を**csadministrator**グループに追加します。

2.  ユーザーオブジェクトが現在ログオンしている場合は、ログオフしてから再びログオンして、新しいグループの割り当てを登録します。
    
    <div>
    

    > [!NOTE]  
    > ユーザーアカウントを、Lync Server 2013、Standard Edition を実行しているサーバーのローカル管理者にすることはできません。 適切なユーザーとグループを CsAdministors グループに追加していない場合、Lync Server 2013 コントロールパネルを開くときにエラーが発生します。これは、"承認されていません。ロールベースのアクセス制御 (RBAC) 認証エラーによりアクセスが拒否されました" というメッセージが表示されます。

    
    </div>

3.  管理者アカウントを使用して、Lync Server コントロールパネルがインストールされているコンピューターにログオンします。

4.  Lync Server コントロールパネルを起動し、メッセージが表示されたら、資格情報を入力します。 Lync Server 2013 コントロールパネルに展開情報が表示されます。

5.  左側のナビゲーションバーで、[**トポロジ**] をクリックし、サービスの状態が緑色の矢印が付いたコンピューターのアイコンであり、展開されてオンラインになった Lync server の各役割の横に緑色のチェックマークが付いていることを確認します。

6.  左側のナビゲーションバーで [**ユーザー**] をクリックし、Lync Server 2013 の2人のユーザーを有効にします。

7.  1人のユーザーをドメインに参加しているコンピューターに、もう一方のユーザーがドメイン内の別のコンピューターにログオンします。

8.  2台の各クライアントコンピューターに Lync Server 2013 をインストールして、両方のユーザーが Lync Server 2013 にサインインして、互いにインスタントメッセージを送信できることを確認します。

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

