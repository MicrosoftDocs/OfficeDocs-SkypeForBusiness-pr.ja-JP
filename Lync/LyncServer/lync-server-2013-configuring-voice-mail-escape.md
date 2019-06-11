---
title: 'Lync Server 2013: ボイスメールのエスケープの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f08e12b97c51d68b4b08d10692802cb035ce8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Lync Server 2013 でボイスメールのエスケープを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

ユーザーが携帯電話への同時着信を構成している場合、携帯電話がオフになっている、バッテリが切れている、または圏外になっているときは、通常、発信者はユーザーの個人ボイス メールにルーティングされます。 Lync Server 2013 を使用すると、ユーザーはビジネス関連の通話を会社のボイスメールシステムにルーティングすることを選択できます。 具体的には、タイマーは構成可能であり、定義された時間内に電話会社のボイスメールによって通話が応答された場合、Lync Server は電話会社のボイスメールシステム (およびユーザーの個人用ボイスメール) から切断されますが、ユーザーの残っている企業システムのエンドポイントは、呼び出しを続けます。 これにより、発信者は自動的にユーザーの会社のボイス メールにルーティングされます。

この構成は、Lync Server Management Shell コマンドレット**CsVoicePolicy**を使用して、ボイスポリシーレベルで次のパラメーターを指定して実行します。

<div>

## <a name="to-configure-voice-mail-escape"></a>ボイス メール エスケープを構成するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  **Set-CsVoicePolicy** に対して次のパラメーターを指定します。
    
      - **EnableVoicemailEscapeTimer** - エスケープ タイマーを有効または無効にします。
    
      - **PSTNVoicemailEscapeTimer**: タイムアウト値をミリ秒単位で指定します。既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。

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

