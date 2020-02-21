---
title: 'Lync Server 2013: ギャラリービューの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f68b4d884671de3ad4e46c7022df8ae0b3d5da09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>Lync Server 2013 でのギャラリービューの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-30_

Lync Server 2013 では、[会議ポリシー] でギャラリービューのビデオ会議を構成します。 ギャラリー ビューは既定で有効になっています。 ギャラリー ビューを許可しない場合、または一部のユーザーにのみ許可する場合は、会議ポリシーを使用して機能を無効にする必要があります。

会議参加者のビデオが利用できない場合、Lync Server 2013 の新機能である高解像度の写真を展開すると、ユーザーのギャラリービューの機能が強化されます。 高解像度の写真は、Active Directory ドメインサービスに保存されている、小さくて制限のある解像度の写真に代わる手段として使用できます。 高解像度写真はユーザーの Exchange 2013 メールボックスに格納されるため、Lync Server 2013 と Exchange 2013 を統合する必要があります。 詳細については、NextHop のブログ記事「Exchange 2013 と Lync Server 2013 の統合」 [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)を参照してください。

<div>


> [!NOTE]  
> 各ブログのコンテンツおよびその URL は予告なしに変更されることがあります。



</div>

ギャラリービューのパラメーターを表示または変更するには、Lync Server 2013 コントロールパネルを使用するか、または次のいずれかのコマンドレットを使用します。

  - **Get-CsConferencingPolicy**

  - **Get-csconferencingpolicy**

  - **Get-csconferencingpolicy**

次の会議ポリシー設定を使用してギャラリー ビューを構成します。

  - **AllowMultiview**   このパラメーターは、ユーザーがギャラリービューのビデオ会議を整理することを許可するかどうかを制御します。 このパラメーターは、ユーザーによって作成されたケジュール済みの会議および臨時の会議に適用されます。
    
    例:
    
      - このパラメーターは、ユーザー A が Lync Server 2013 プールに所属している場合は True に設定されます。 ユーザー A が開催する会議では、ユーザーは会議に参加し複数のビデオ ストリームを受信できます。
    
      - このパラメーターは、ユーザー B が Lync Server 2013 プールに所属している場合は False に設定されます。 ユーザー B によって開催された会議には、Lync Server 2010 によって提供されるビデオ会議のような単一のビデオストリームがあります。
    
    このパラメーターにより、複数のビデオ ストリームが許可される会議を開催できるユーザーが決定します。複数のビデオ ストリームが許可される会議の参加者は、個々のアクセス許可に応じて、複数のビデオ ストリームを受信できたりできなかったりします (EnableMultiviewJoin パラメーターの説明を参照してください)。

  - **EnableMultiviewJoin**   このパラメーターは、会議の参加者が、許可する会議でのギャラリービューのビデオ表示を受信するかどうかを制御します。 このパラメーターは、ユーザーが参加する会議でのユーザー エクスペリエンスを管理します。
    
    例:
    
      - ユーザー c の場合、このパラメーターは True に設定されます。ユーザー C は、会議に参加しているとき、またはユーザー A が開始したときに、複数のビデオストリームを受信できます。ユーザー C は、Lync Server 2010 で提供されているビデオ会議の場合と同様のビデオストリームを1つ受信します。ユーザー B によって開催または開始された会議への参加。
    
      - User d では、このパラメーターは False に設定されています。ユーザー A またはユーザー B が開催した会議に参加するときに、Lync Server 2010 によって提供されるビデオ会議の場合と同様のビデオストリームが1つずつ受信されます。

次の手順では、Lync Server 管理シェルを使用してギャラリービューのビデオ会議を有効にする例を示します。

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>ギャラリー ビューのビデオ会議用の会議ポリシーを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  コマンド ラインで次のコマンドレットを実行して、会議ポリシーを編集します。
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

