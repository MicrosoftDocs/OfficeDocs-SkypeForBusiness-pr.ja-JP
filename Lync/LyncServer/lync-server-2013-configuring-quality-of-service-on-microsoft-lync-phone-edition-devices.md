---
title: Microsoft Lync Phone Edition デバイスでのサービス品質の設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Lync Server 2013 での Microsoft Lync Phone Edition デバイスでのサービス品質の設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

IPhones などのデバイスでは、サービスの品質 (QoS) は既定で有効になっていませんが、Lync Phone Edition を実行しているデバイスでは既定で QoS が有効になっています。 (これらのデバイスは、一般的に UC またはユニファイドコミュニケーション電話と呼ばれます)。これを確認するには、Lync Server 管理シェルで次の Windows PowerShell コマンドを実行します。

    Get-CsUCPhoneConfiguration

UC 電話構成設定を変更していない場合は、次のような情報が表示されます。

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

サービスの品質を向上させるには、これらのプロパティのいずれか1つだけを VoiceDiffServTag します。 VoiceDiffServTag は、Lync Phone Edition デバイスから emanating ボイストラフィックに割り当てられた DSCP 値を表します。

<div>


> [!NOTE]
> Voice8021p パラメーターは、Lync Server 2013 ではサポートされなくなりました。 このパラメーターは、Microsoft Lync Server 2010 との下位互換性を維持するために有効です。ただし、Lync Server 2013 で使用されているデバイスには影響はありません。



</div>

ほとんどのネットワークでは、Lync Phone Edition のパケットに40の VoiceDiffServTag をマークすると、問題が発生しないようにする必要があります。 ただし、40は、通常はオーディオトラフィックに使用される値ではありません。代わりに、ほとんどの場合、音声トラフィックは DSCP コード46でマークされます。 ネットワーク全体の一貫性を維持するために、UC 携帯電話の VoiceDiffServTag プロパティを46に変更したい場合があります。

そのためには、Windows PowerShell または Lync Server コントロールパネルのいずれかを使うことができます。 Windows PowerShell を使用して VoiceDiffServTag の値を変更するには、Lync Server 管理シェルで次のコマンドを実行します。

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

上記のコマンドは、UC 電話構成設定のグローバルコレクションを変更します。 ただし、そのような UC の携帯電話の設定をサイトの範囲に割り当てることもできます。 UC 電話構成の設定をサイトの範囲で変更するには、サイト Id を指定する必要があります。 次に例を示します。

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

以下のコマンドを使用して、すべての UC 電話構成設定を同時に変更することもできます。

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Lync Server コントロールパネルを使用してこの変更を行う場合は、[コントロールパネル] を起動し、次の手順を実行します。

1.  [**クライアント**] をクリックし、[**デバイスの構成**] をクリックします。

2.  [**デバイスの構成**] タブで、変更する設定のコレクション ([**グローバル**] など) をダブルクリックします。

3.  [**デバイス構成の編集**] ダイアログボックスで、[**ボイスの品質 (QoS)** ] ボックスの値を**46**に設定し、[**コミット**] をクリックします。

複数のコレクションがある場合は、UC の電話設定のコレクションごとにこの手順を繰り返す必要があります。 Lync Server コントロールパネルでは、複数の設定コレクションを同時に変更することはできません。

組織内の Windows オペレーティングシステム (iPhones など) に基づいていないデバイスを使用している場合、これらのデバイスは、VoiceDiffServTag 設定の変更によって影響を受けません。 これらのデバイスで DSCP 値を変更する場合は、各デバイスの種類について、管理者マニュアルを参照する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

