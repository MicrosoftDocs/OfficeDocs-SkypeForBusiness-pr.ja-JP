---
title: 場所を手動で取得するためのユーザーエクスペリエンスの定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5913547ab7d5030ca40070de36b4deb1f6a89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>Lync Server 2013 で場所を手動で取得するときのユーザーエクスペリエンスの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

クライアントがネットワークの外部にいる場合、または定義されていないサブネットにいる場合は、ユーザーは場所を手動で入力できます。ただし緊急通報の場合の通話は、緊急情報受信センター (PSAP) にルーティングされる前に、最初に国または地域の E9-1-1 Emergency Call Response Center (ECRC) のディスパッチャーにルーティングされます。ECRC は言葉で発信者に場所を問い合わせた後、提供された情報に基づいて、適切な PSAP に通話を転送します。

  - **場所情報サービスによって自動的に指定されていない場合に、場所の入力を求めるメッセージが表示されるようにしますか?**  
    たとえば、クライアントが未定義のサブネット、自宅、ホテル、またはネットワーク外部のいずれかの場所に存在する場合は、ユーザーに場所の入力を求める必要があるでしょうか。
    
    場所ポリシーの [**場所の入力を求める**] 設定を構成し、クライアントの動作を定義できます。この値を [いいえ] に設定すると、ユーザーは場所の入力を求められません。この値を [はい] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。この値を [免責事項] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉じようとすると免責事項が表示されます。すべての場合において、ユーザーは通常どおりクライアントを使用し続けることができます。

ユーザーが場所を手動で入力すると、クライアントのネットワークでの既定のゲートウェイの MAC アドレスに場所がマップされ、クライアントにあるユーザーごとのテーブルに保存されます。 ユーザーが既に保存されている場所に戻ると、Lync クライアントはその場所に自動的に設定します。

<div>


> [!NOTE]
> 変更できるのはクライアントの現在の場所だけですが、ローカル ユーザーのテーブルに格納されている場所を削除することもできます。



</div>

</div>

<span> </span>

</div>

</div>

</div>

