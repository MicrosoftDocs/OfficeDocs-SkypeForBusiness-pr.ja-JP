---
title: Microsoft Lync Phone Edition デバイスでのサービスの品質の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b1dd5fd119022807fbc64218c80e24a33557aa1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Lync Server 2013 での Microsoft Lync Phone Edition デバイスでのサービスの品質の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

IPhones などのデバイスでは、サービスの品質 (QoS) は既定で有効になっていませんが、Lync Phone Edition を実行しているデバイスでは既定で QoS が有効になっています。 (これらのデバイスは一般に UC またはユニファイドコミュニケーション電話と呼ばれます)。これを確認するには、Lync Server 管理シェルで次の Windows PowerShell コマンドを実行します。

    Get-CsUCPhoneConfiguration

UC 電話の構成設定を変更していなければ、次のような情報が返されます。

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

これらのプロパティのうち、サービスの品質に関連するのは VoiceDiffServTag だけです。 VoiceDiffServTag は、Lync Phone Edition デバイスからの音声トラフィック emanating に割り当てられた DSCP 値を表します。

<div>


> [!NOTE]
> Voice8021p パラメーターは、Lync Server 2013 ではサポートされなくなりました。 このパラメーターは、Microsoft Lync Server 2010 との下位互換性を維持するために有効になっています。ただし、Lync Server 2013 で使用されているデバイスには影響を与えません。



</div>

ほとんどのネットワークでは、Lync Phone Edition のパケットに40の VoiceDiffServTag をマークすると、問題が発生しないようにする必要があります。 音声トラフィックは、ほとんど常に DSCP コード 46 でマーキングされます。 ネットワーク全体の一貫性を確保するために、UC 電話の VoiceDiffServTag プロパティを 46 に変更することをお勧めします。

これを行うには、Windows PowerShell または Lync Server コントロールパネルのどちらかを使用できます。 Windows PowerShell を使用して VoiceDiffServTag の値を変更するには、Lync Server 管理シェルで次のコマンドを実行します。

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

上のコマンドは、UC 電話構成設定のグローバル コレクションを変更します。UC 電話設定は、サイト スコープに割り当てることもできます。UC 電話構成設定をサイト スコープで変更するには、サイト ID を指定する必要があります。次に例を示します。

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

次のコマンドを使用して、すべての UC 電話構成設定を同時に変更することもできます。

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

この変更を Lync Server コントロールパネルを使用して行う場合は、[コントロールパネル] を起動し、次の手順を実行します。

1.  [**クライアント**] をクリックして、[**デバイス構成**] をクリックします。

2.  [**デバイス構成**] タブで、変更する設定のコレクションをダブルクリックします ([**グローバル**] など)。

3.  [**デバイス構成の編集**] ダイアログ ボックスで、[**音声のサービス品質 (QoS)**] ボックスの値を **46** に設定し、[**確定**] をクリックします。

複数のコレクションがある場合は、UC 電話設定の各コレクションに対してこのプロセスを繰り返す必要があります。 Lync Server コントロールパネルでは、複数の設定コレクションを同時に変更することはできません。

Windows オペレーティング システム ベースではないデバイス (iPhone など) がある場合、VoiceDiffServTag の設定を変更しても、それらのデバイスには影響しません。それらのデバイスの DSCP 値を変更するには、そのデバイスの管理マニュアルを参照する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

