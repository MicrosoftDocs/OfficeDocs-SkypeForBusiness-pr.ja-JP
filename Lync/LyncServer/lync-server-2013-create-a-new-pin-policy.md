---
title: 'Lync Server 2013: 新しい PIN ポリシーを作成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new PIN policy
ms:assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182547(v=OCS.15)
ms:contentKeyID: 48184777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c381e33c54f38bfdb00f968885dafa85184018b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-pin-policy-in-lync-server-2013"></a>Lync Server 2013 で新しい PIN ポリシーを作成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-19_

[ **Pin のポリシー** ] ページを使用して、IP 電話で Lync 2013 に接続しているユーザーに暗証番号 (pin) 認証を提供できます。 PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。 詳細については、「 [Lync Server 2013 で既存の Web サービスの構成の設定を変更](lync-server-2013-modify-existing-web-service-configuration-settings.md)する」を参照してください。

ユーザーレベルまたはサイトレベルの PIN ポリシーを作成するには、次の手順を実行します。

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a>ユーザーまたはサイトの PIN ポリシーを作成するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。

4.  [**PIN ポリシー**] ページで [**新規**] をクリックして、次のいずれかを実行します。
    
      - ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。[**新しい PIN ポリシー**] の [**名前**] に、ポリシーを説明する名前を入力します。
    
      - サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。[**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。

5.  [**説明**] フィールドに、PIN ポリシーの説明を入力します。

6.  [**最小 PIN サイズ**] フィールドで、許可する PIN の最小サイズを入力または選択します。既定の最小サイズは 5 桁です。

7.  ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。既定では、最大試行回数は自動的に決定されます。

8.  [**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。

9.  PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。このオプションをオンにしない限り、PIN が期限切れになることはありません。既定では、PIN に有効期限はありません。

10. [**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。

11. [**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。既定では、ユーザーは自分の PIN を再利用できます。

12. PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。既定では、複雑なパターンの数字のみが許可されます。
    
    <div>
    

    > [!IMPORTANT]  
    > 共通のパターンは許可しないことをお勧めします。

    
    </div>

13. [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

