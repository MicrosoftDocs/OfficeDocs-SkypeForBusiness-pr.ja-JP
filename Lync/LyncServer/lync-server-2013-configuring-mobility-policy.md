---
title: 'Lync Server 2013: モビリティポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6410e50a5e7d84de152b9a4e4bd1f962c5a3c9bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Lync Server 2013 でのモビリティポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 には、モビリティ機能を使用できるユーザー、勤務先から通話、ボイスオーバー IP (VoIP) またはビデオ、および VoIP またはビデオのどちらかに Wi-fi が必要かどうかを決定するモビリティポリシーが用意されています。 Via for Work 機能を使用すると、モバイルユーザーは携帯電話番号ではなく勤務先電話番号を使用して、携帯電話で通話を発信および受信することができます。 この機能により、呼び出し元の携帯電話番号が表示されないようにし、ユーザーが発信通話料金を回避することができます。 VoIP およびビデオを構成することにより、ユーザーは VoIP 通話とビデオを受信できます。 WiFi 使用法の設定ユーザーのデバイスが、携帯データネットワーク経由で WiFi ネットワークを使用する必要があるかどうかを定義します。

既定では、モビリティ、勤務先から通話、および VoIP およびビデオの機能が有効になっています。 VoIp およびビデオ用に WiFi を必須にする設定は無効になっています。 管理者は、コマンドレットを実行して、これらの機能にアクセスできるユーザーを指定できます。 オプションは、グローバル、サイト別、またはユーザー別に無効にできます。

モビリティ機能および [勤務先から通話] を使用できるためには、ユーザーが次の前提条件を満たしている必要があります。

  - ユーザーが Lync Server 2013 に対して有効になっている必要があります。

  - ユーザーは、エンタープライズ VoIP に対して有効になっている必要があります。

  - ユーザーには、**EnableMobility** オプションが True に設定されているモビリティ ポリシーが割り当てられている必要があります。

ユーザーが [勤務先から通話] を使用できるためには、ユーザーは次の 2 つの追加の前提条件を満たす必要があります。

  - ユーザーには、[**電話の同時呼び出しを有効にする**] オプションが選択されている音声ポリシーが割り当てられている必要があります。

  - ユーザーには、**EnableOutsideVoice** オプションが True に設定されているモビリティ ポリシーが割り当てられている必要があります。

<div>


> [!NOTE]  
> エンタープライズ Voip が有効になっていないユーザーは、モバイルデバイスを使用して Lync Voice over IP (VoIP) 通話を行うことができます。または、自分のモバイルデバイスで [クリックして参加] リンクを使用して会議に参加できます。これらのユーザーに音声ポリシーの適切なオプションを割り当てる場合。 詳細については、「 <A href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013 のモビリティ要件の定義</A>」を参照してください。



</div>

Lync Server 2013 でユーザーを有効にする方法の詳細については、「 [Lync server 2013 のユーザーアカウントの無効化または再有効化](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。 エンタープライズ Voip に対するユーザーの有効化の詳細については、「 [Enable users For Enterprise voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。 音声ポリシーオプションの設定の詳細については、「 [Modify a voice policy」および「CONFIGURE PSTN usage records In Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)」を参照してください。

<div>

## <a name="to-modify-global-mobility-policy"></a>グローバル モビリティ ポリシーを変更するには

1.  Lync Server 管理シェルと Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  モビリティおよび [勤務先から通話] へのアクセスをグローバルに無効にします。コマンド ラインで、次のように入力します。
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > モビリティへのアクセスをオフにしなくても "勤務先から通話" をオフにできます。ただし、モビリティをオフにする場合は、"勤務先から通話" もオフにする必要があります。

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>モビリティ ポリシーをサイト別に変更するには

1.  Lync Server 管理シェルと Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  サイトレベルのポリシーを作成し、VoIP およびビデオをオフにして、IP オーディオと IP ビデオをサイトごとに有効にすることができます。 コマンドラインで、次のように入力します。
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>モビリティ ポリシーをユーザー別に変更するには

1.  Lync Server 管理シェルと Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  ユーザー レベルのモビリティ ポリシーを作成し、モビリティと [勤務先から通話] をユーザー別に無効にします。コマンド ラインで、次のように入力します。
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    モビリティへのアクセスをオフにしなくても "勤務先から通話" をオフにできます。ただし、モビリティをオフにする場合は、"勤務先から通話" もオフにする必要があります。
    
    たとえば、次のようになります。
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のユーザーアカウントを無効または再度有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Lync Server 2013 のモビリティ要件の定義](lync-server-2013-defining-your-mobility-requirements.md)  


[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

