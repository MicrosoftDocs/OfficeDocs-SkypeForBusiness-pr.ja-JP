---
title: 'Lync Server 2013: ギャラリービューを構成する'
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
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>Lync Server 2013 でギャラリービューを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-30_

Lync Server 2013 では、会議ポリシーの [ビデオ会議] を構成します。 ギャラリービューは既定でオンになっています。 ギャラリービューを許可しない場合、または一部のユーザーのみに許可する場合は、会議ポリシーのこの機能を無効にする必要があります。

会議参加者のビデオが利用できない場合は、Lync Server 2013 の新機能である高解像度の写真を展開すると、ユーザーのギャラリービューエクスペリエンスが向上します。 高解像度の写真は、Active Directory ドメインサービスに保存されている小型の限定された解像度の連絡先写真の代わりとなるものです。 高解像度の写真はユーザーの Exchange 2013 メールボックスに保存されるため、Lync Server 2013 を Exchange 2013 と統合する必要があります。 詳細については、「NextHop のブログ記事、「Exchange 2013 と Lync Server 2013 の[http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)統合」を参照してください。

<div>


> [!NOTE]  
> 各ブログの内容と URL は、将来予告なしに変更されることがあります。



</div>

ギャラリーの表示パラメーターを表示または変更するには、Lync Server 2013 コントロールパネルを使用するか、次のいずれかのコマンドレットを使用します。

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

以下の会議ポリシー設定を使用して、ギャラリービューを構成します。

  - **AllowMultiview**   このパラメーターは、ユーザーがギャラリービューのビデオ会議を整理することを許可されているかどうかを制御します。 このパラメーターは、ユーザーが作成したスケジュールされた会議と臨時の会議に適用されます。
    
    たとえば
    
      - ユーザー A が Lync Server 2013 プールをホームにしている場合は、このパラメーターを True に設定します。 ユーザーによって開催された会議複数のビデオストリームの参加と受信を可能にします。
    
      - ユーザー B が Lync Server 2013 プールをホームにしている場合は、このパラメーターを False に設定します。 ユーザー B によって開催された会議には、Lync Server 2010 によって提供されるビデオ会議エクスペリエンスに似た1つのビデオストリームがあります。
    
    このパラメーターは、複数のビデオストリームを許可する会議を開催できるユーザーを指定します。 複数のビデオストリームを許可する会議の参加者は、個別のアクセス許可に基づいて複数のビデオストリームを受信することは許可されない場合があります (EnableMultiviewJoin パラメーターの説明を参照してください)。

  - **EnableMultiviewJoin**   このパラメーターは、会議の参加者が、会議で許可されているギャラリーの表示ビデオエクスペリエンスを受け取るかどうかを制御します。 このパラメーターは、ユーザーが参加している会議でのユーザーエクスペリエンスを制御します。
    
    たとえば
    
      - ユーザー c の場合、このパラメーターは True に設定されます。ユーザー A は、会議に参加している場合、またはユーザー A が開始した場合に、複数のビデオストリームを受け取ることができます。ユーザー C は、Lync Server 2010 によって提供されるビデオ会議と同様のビデオストリームを1つ受信します。ユーザー B によって開催または開始された会議への参加。
    
      - ユーザー D の場合、このパラメーターは False に設定されます。ユーザー D は、ユーザー A またはユーザー B によって開催された会議に参加しているときに、Lync Server 2010 によって提供されるビデオ会議エクスペリエンスと同様の単一のビデオストリームを受け取ります。

次の手順では、Lync Server 管理シェルを使って、ギャラリービューのビデオ会議を有効にする例を示します。

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>ギャラリービューのビデオ会議用の会議ポリシーを変更するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  コマンドラインで、次のコマンドレットを実行して会議ポリシーを編集します。
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

