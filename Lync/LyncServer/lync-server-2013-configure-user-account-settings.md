---
title: 'Lync Server 2013: ユーザーアカウント設定の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71628f056298965f4033dc6bbecbe75b47b678a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520204"
---
# <a name="configure-user-account-settings-in-lync-server-2013"></a>Lync Server 2013 でユーザーアカウント設定を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

ダイヤルイン ユーザーは各自の電話番号または内線番号、それに PIN を入力し、認証されたユーザーとして会議に参加します。 Lync Server ユーザーアカウントで指定されたテレフォニー **回線 URI** は、認証に必要です。

このトピックの手順は、**[回線 URI]** を 1 つのユーザー アカウントに対して割り当てる方法について説明します。 **[回線 URI]** を複数のユーザー アカウントに対して割り当てる必要がある場合は、**Set-CsUser** コマンドレットを使用するスクリプトを作成できます。 サンプルスクリプトを使用して複数のユーザーアカウントに **回線 uri** を割り当てる方法の詳細については、「」の「複数のユーザーに回線 Uri を割り当てる」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945) 。

<div>

## <a name="to-configure-user-account-settings"></a>ユーザー アカウント設定を構成するには

1.  RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**Cs-UserAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで **[ユーザー]** をクリックします。

4.  検索フィールドで、ダイヤルイン会議の構成を行うユーザーの名前を入力するか、**[フィルターの追加]** をクリックして検索フィールドを指定し、次に **[検索]** をクリックします。

5.  ユーザー名をダブルクリックして、[ **Lync Server ユーザーの編集** ] ダイアログボックスを開きます。

6.  **[テレフォニー]** の下の **"回線 URI"** フィールドで、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。
    
    <div>
    

    > [!NOTE]  
    > [ <STRONG>回線 URI</STRONG> ] を指定できるのは、[ <STRONG>テレフォニー</STRONG> ] が [ <STRONG>pc 間のみ</STRONG>]、[ <STRONG>エンタープライズ voip</STRONG>]、[ <STRONG>リモート通話コントロール</STRONG> ]、または [ <STRONG>リモート通話コントロールのみ</STRONG>] に設定されている場合のみです。

    
    </div>

7.  [**確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

