---
title: 'Lync Server 2013: プライベート電話回線の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0369ea671860b29c8cf7f7e1d9e0b894770c6d6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>Lync Server 2013 を使用したプライベート電話回線の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-11_

Lync Server 2013 には、プライマリ電話回線に加えて、2番目のプライベート電話回線をユーザーに提供する機能が導入されています。 プライベート電話回線は、多くの場合、役員や直接受信できる非公開の電話番号が必要なユーザーに割り当てられます。

プライベート電話回線は、Lync Server 管理シェルでのみ構成できます。 Lync Server コントロールパネルを使用してプライベート電話回線を構成することはできません。 プライベート電話回線は、混在展開ではなく、Lync Server の展開でのみ構成する必要があります。

<div>

## <a name="characteristics-of-private-telephone-lines"></a>プライベート電話回線の特徴

セカンダリのプライベート電話回線の概念は基本的に単純なものですが、プライベート番号の特徴およびユーザーのプライマリ電話回線との類似点と相違点を理解することが重要です。

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>プライベート電話回線の一般的特徴

  - ユーザーに割り当てることができるプライベート電話回線は 1 つのみです。

  - プライベート電話回線が割り当てられたユーザーには、ボイス メール用メールボックスは 1 つのみ設定され、不在着信通知は 1 つの電子メール アドレスに通知されます。

  - プライベート電話回線が割り当てられたユーザーに、2 番目の SIP アドレスは割り当てられません。また、セカンダリのプライベート電話回線によって、ユーザーにネットワーク上の 2 番目のプレゼンス (2 番目のインスタント メッセージング ID など) は付与されません。

  - プライベート電話回線は、内部設置型展開でのみ使用できます。 これらは、Lync Server のホスト型展開では使用できません。

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>プライベート電話回線とプライマリ電話回線の相違点

  - プライベート電話回線の電話番号は、電話帳や Active Directory ドメイン サービスから得られる連絡先リストには表示されません。

  - プライベート電話回線では、着信の転送、チーム呼び出し、委任、チーム呼び出し、グループ通話ピックアップ、応答グループアプリケーションの各機能は使用できません。

  - プライベート電話回線の呼び出しには特別な呼び出し音が設定され、呼び出しのシステム通知により、プライベート番号に着信通話があることがユーザーに通知されます。

  - プライベート電話回線の呼び出しは、常に直接行われます。 "応答不可" ルールには従いません。

  - プライベート電話回線は着信のみで、発信通話に使用することはできません。 プライベート電話回線を割り当てられたユーザーが電話をかけた場合、その通話はユーザーのプライマリ電話回線から発信され、ユーザーの名前やプライマリ電話番号は通話先に対して非表示にはなりません。

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>プライベート電話回線とプライマリ電話回線の類似点

  - プライベート電話回線の呼び出しで応答のなかったものは、プライマリ電話回線のものと同じボイス メール用受信ボックス (ボイス メールが有効になっている場合) にルーティングされます。

  - コール パークとコール ピックアップは、ユーザーのプライマリ電話回線の場合とまったく同じ方法で、プライベート電話回線で機能します。

  - ユーザーのプライマリ電話回線で同時呼び出しが有効になっている場合、プライベート電話回線でも有効になります。

  - プライベート電話回線の電話番号は、ユーザーのプライマリ電話回線の電話番号と同じ方法で詳細な通話の記録に記録されますが、プライベート電話番号であることが表示されます。

  - ユーザーがプライベート電話回線で通話に応答した場合、その通話はユーザーのプライマリ電話回線の通話と同じように処理されます。 たとえば、プライベート電話回線で通話を受信するユーザーが通話を転送したり、他のユーザーを電話会議に招待したりすると、ユーザーの名前が Lync 2013 に表示され、ユーザーのプライマリ電話回線の電話番号が発信者番号に表示されます。

  - ユーザーは、プライマリ電話回線と同じ方法で、プライベート電話回線からの通話を切り替える (応答する前に、携帯電話や自宅の電話などの別の宛先に通話をリダイレクトする) ことができます。
    
    <div>
    

    > [!NOTE]  
    > プライベート番号の呼び出しが別の電話番号にルーティングされた場合、その別の電話番号でプライベート電話回線の電話番号を使用できるようになり、その番号のログを表示できます。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 会議からプライベート電話回線への呼び出しでは、着信システム通知に<EM>プライベート番号</EM>表示は行われません。

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>プライベート電話回線の管理

プライベート電話回線の作成および管理の技術的な側面に加えて、プライベート電話回線用の回線管理手順を設定する必要があります。これには、組織内のプライベート番号の対象ユーザー向けのポリシーの指定、それらのユーザーとその電話番号の一覧の作成および管理、役員のプライベート電話帳の作成、ユーザー トレーニングの調整、関連する作業などがあります。

<div>


> [!NOTE]  
> プライベート電話回線は、Active Directory にユーザー オブジェクトの msRTCSIP-PrivateLine 属性として格納されます。既定では、Authenticated Users グループのメンバーは、この属性に対して読み取りアクセスを持ちます。



</div>

<div>

## <a name="assigning-telephone-numbers"></a>電話番号の割り当て

プライベート電話回線を必要とする新規ユーザーのアカウントは、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、プライベート電話回線のないアカウントと同じ方法で作成されます。

Lync Server 管理シェルで sip:joe@contoso.com**コマンドレットを使用して、** ユーザーのプライベート電話回線に電話番号を割り当てます。たとえば、「 **Set-Csuser-Identity ""-PrivateLine "Tel: + 14255551212"」** のようにします。

プライベート電話回線の電話番号の長さは 3 ~ 15 桁で、前に "TEL:" というプレフィックスを付ける必要があります。 組織で市外局番や国/地域コードに Direct Inward Dialing を使用している場合、その市外局番や国/地域コードを指定できます。

コマンドレットおよび Lync Server 管理シェルの詳細については、「 [Lync server 2013 Management shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>混在環境におけるプライベート電話回線

プライベート電話回線は、Lync Server の展開に対してのみ構成する必要があります。 Lync Server と Office Communications server 2007 または Office Communications Server 2007 R2 サーバーの両方が存在する展開では、以前のバージョンのユーザーがプライベート電話回線への呼び出しを試みると、呼び出しのルーティングが失敗します。サーバーがプライベート電話回線で逆引き番号検索を実行します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

