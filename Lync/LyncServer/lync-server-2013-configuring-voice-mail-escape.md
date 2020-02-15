---
title: 'Lync Server 2013: ボイスメールエスケープの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 131b36b87a3d930662cdd863dd4ebc1d0d69163e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Lync Server 2013 でのボイスメールエスケープの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

ユーザーが携帯電話に同時呼び出しを構成すると、携帯電話がオフになっている場合、バッテリ電源が切れている場合、または範囲外にある場合、通常、発信者はユーザーの個人ボイスメールにルーティングされます。 Lync Server 2013 を使用すると、ユーザーは会社のボイスメールシステムにビジネス関連の通話をルーティングすることを選択できます。 具体的には、タイマーを構成することができ、定義された時間範囲内の電話会社のボイスメールによって通話が応答されると、Lync Server は、その電話会社のボイスメールシステム (およびユーザーの個人用ボイスメール) から切断され、ユーザーの残りの企業システムのエンドポイントは、呼び出しを続行します。 これにより、発信者は自動的にユーザーの会社のボイス メールにルーティングされます。

この構成は、Lync Server 管理シェルコマンドレット Set-csvoicepolicy を使用して、音声ポリシーレベルで次のパラメーターを**設定**して実行します。

<div>

## <a name="to-configure-voice-mail-escape"></a>ボイスメールエスケープを構成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  **Set-csvoicepolicy**に次のパラメーターを指定します。
    
      - **EnableVoicemailEscapeTimer** -エスケープタイマーを有効または無効にします。
    
      - **PSTNVoicemailEscapeTimer** -タイムアウト値をミリ秒単位で指定します。 既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。

</div>

<div>

## <a name="example"></a>例

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

