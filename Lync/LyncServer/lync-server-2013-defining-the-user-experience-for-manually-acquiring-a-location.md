---
title: 手動で場所を取得するためのユーザーの作業を定義する
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
ms.openlocfilehash: 20bd88f9c9f619e67c9aec8f6b0111320fa3ed2d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>Lync Server 2013 で手動で場所を取得するためのユーザーの作業を定義する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

クライアントがネットワークの外部にいる場合、または定義されていないサブネットにいる場合は、ユーザーは場所を手入力できます。ただし緊急通報の際の通話は、緊急情報受信センター (PSAP) にルーティングされる前に、最初に国または地域の E9-1-1 Emergency Call Response Center (ECRC) のディスパッチャーにルーティングされます。ECRC は言葉で発信者に場所を問い合わせた後、提供された情報に基づいて、適切な PSAP に通話を転送します。

  - **場所情報サービスによってユーザーが自動的に提供されない場合に、場所の入力を求めるメッセージが表示されるようにしますか。**  
    たとえば、クライアントが未定義のサブネット、自宅、ホテル、またはどこであれネットワークの外部に存在する場合は、ユーザーに場所の入力を求める必要があるでしょうか。
    
    場所ポリシーの [**場所の入力を求める**] 設定を構成し、クライアントの動作を定義できます。この値を [いいえ] に設定すると、ユーザーは場所の入力を求められません。この値を [はい] に設定すると、ユーザーは場所の入力を求められますが、入力せずにプロンプトを閉じることもできます。この値を [免責事項] に設定すると、ユーザーは場所の入力を求められ、入力せずにプロンプトを閉ようとすると免責事項が表示されます。すべての場合において、ユーザーは通常どおりクライアントを使用し続けることができます。

ユーザーが場所を手入力すると、クライアントのネットワークでの既定のゲートウェイの MAC アドレスに場所がマップされ、クライアントにあるユーザーごとのテーブルに保存されます。ユーザーが以前に保存されたいずれかの場所を返すと、Lync クライアントは自動的にその場所を設定します。

<div>


> [!NOTE]
> 変更できるのはクライアントの現在の場所だけですが、ローカル ユーザーのテーブルに格納されている場所を削除することもできます。



</div>

</div>

<span> </span>

</div>

</div>

</div>

