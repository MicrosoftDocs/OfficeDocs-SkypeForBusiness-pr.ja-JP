---
title: 常設チャットのメンバーシップについて
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cc357eff6cdc68c5285eeb915f5534b6f38b871
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>常設チャットのメンバーシップについて

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

常設チャットルームへのユーザーアクセスは、メンバーシップによって管理されます。ユーザーがメッセージを投稿および閲覧できるようにするには、チャットルームのメンバーである必要があります。 チャットルームへの指定された所属を持つ**プレゼンター**のみが、大**会議室への投稿**を使用できます。 大会議室は、発表者**のみが投稿**でき、全員が閲覧できるチャットルームの一種です。

また、常設チャットルームは、カテゴリのルールの下で動作します。 カテゴリの詳細については、このトピックで後述する「 [Lync Server 2013 でのカテゴリ、ルーム、およびアドインの管理](lync-server-2013-managing-categories-rooms-and-add-ins.md)」と「カテゴリのスコープの適用方法」および「ルームのカテゴリの戦略」を参照してください。

常設チャット管理者は、チャットルームのカテゴリを作成および管理できます。 チャットルームカテゴリの作成と管理の一環として、常設チャット管理者は、特定のカテゴリのチャットルームのメンバーまたはクリエーターにアクセスできるプリンシパル (Active Directory ドメインサービスグループ、コンテナー、ユーザー) を構成できます。

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Active Directory ドメインサービスと常設チャット

常設チャットサーバーは、内部の常設チャットユーザーのプールに対して Active Directory に依存します。 常設チャット (クライアント) をインストールした後、ユーザーおよびユーザーグループのドメインをルームカテゴリに追加することができます。 その後、ルーム カテゴリのメンバーシップにそれらのユーザーとグループを追加できます。

<div>


> [!IMPORTANT]  
> 常設チャットルームに変更を加える必要があるユーザーには、重複する名前がないことを確認する必要があります。 ユーザー名が重複している場合は別の名前に変更し、ユーザーによる変更の実行を許可してください。 Active Directory で名前が重複していて、そのユーザーの会議室での変更を試行すると、エラーメッセージが表示され、ユーザーは管理者に連絡して解決策を求めることができます。



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>カテゴリの範囲指定のしくみ

カテゴリは、その**Allowedmembers**プロパティに基づいて、そのカテゴリの常設チャットルームのメンバーシップリストのメンバーになることができるすべてのユーザーとグループを指定します。 たとえば、カテゴリの**Allowedmembers**を contoso.com に設定すると、 *contoso*の任意のグループまたはユーザーをそのカテゴリのチャットルームにメンバーとして追加できます。 カテゴリの **AllowedMembers** を "営業**" に設定した場合は、その配布リスト内のグループとユーザーのみを、カテゴリ内のチャット ルームにメンバーとして追加できます。 同様に、**Creators** プロパティを使用すると、カテゴリ内にチャット ルームを作成できるユーザーを制御できます。 チャット ルームが作成されると、**AllowedMembers** グループのユーザーを、ルームで進行中の管理操作 (メンバーシップの変更や承認など) の**管理者**として指定できます。

カテゴリの **AllowedMembers** と **Creators** を定義すると、次の利点が得られます。

  - カテゴリ内のすべてのチャット ルームがカテゴリ レベルの制限のセットにバインドされます。これにより、業務ニーズとアクセス ポリシーに基づいてチャット ルームを分離できます。

  - **Creators** の一覧に含まれるユーザーが、カテゴリ内に新しいチャット ルームを作成できます。チャット ルームを作成できる組織内の担当者の数が制限されているシステムを実装する場合は、この制御を使用して要件を満たすことができます。

</div>

<div>

## <a name="room-category-strategies"></a>ルーム カテゴリの戦略

カテゴリの**Allowedmembers**には、このカテゴリの常設チャットルームを使用するすべてのユーザーが含まれている必要があります。 業務データを保護し、適切なレベルのアクセスを確保するための要件に応じて、ルームの検索およびルームへの参加が可能なユーザーを指定する 1 つ以上のカテゴリの定義が必要な場合があります。 ルームの作成を特定のユーザー グループ (中央のヘルプデスク、またはフルタイム勤務の従業員のみ) にのみ許可する場合は、要件を満たすカテゴリの **Creators** を絞り込むことができます。

また、カテゴリを使用して倫理的境界を作成することもできます。倫理的境界を使用すると、組織内における利害の対立を避けることができます。たとえば、管理者は、トレーダー専用のカテゴリやアナリスト専用のカテゴリにチャット ルームを作成できます。

<div>


> [!NOTE]  
> Lync Server 2013 の常設チャットサーバーでは、フェデレーションユーザーへのアクセスはサポートされていません。 以前のバージョンの常設チャットサーバーのフェデレーションユーザーからチャットがある場合、それらは移行されます。 フェデレーション ユーザーは、無効なプリンシパルとして追加されます。



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>ユーザー グループへのメンバーの絞り込み

カテゴリにドメインを追加する場合は、そのドメインにグループ オブジェクトが含まれているユーザー グループをカテゴリ内のルームのメンバーとして指定できます。

カテゴリの**Allowedmembers**および**クリエーター**を定義するために、ドメインや組織単位などの Active Directory コンテナーを使用することをお勧めします。 **AllowedMembers** または **Creators** の一覧には任意のドメインのオブジェクトを追加できます。 カテゴリ内のルームに追加できるのは、**AllowedMembers** または **Creators** の一覧に含まれるオブジェクトのみです。

</div>

</div>

<span> </span>

</div>

</div>

</div>

