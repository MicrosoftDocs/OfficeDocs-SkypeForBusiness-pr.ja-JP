---
title: 'Lync Server 2013: モビリティ ポリシーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Lync Server 2013 でのモビリティ ポリシーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 は、モバイル機能を使用できるユーザー、勤務先での通話、ボイスオーバー IP (VoIP)、またはビデオ、または VoIP とビデオのどちらで WiFi が必要かを決定するためのモビリティーポリシーを提供します。 [職場での通話] 機能を使うと、携帯電話の電話番号ではなく勤務先の電話番号を使用して、携帯電話で通話を発信および受信することができます。 この機能により、通話発信者の携帯電話番号が表示されず、ユーザーが送信通話料金を回避することができます。 VoIP とビデオを設定することで、ユーザーは VoIP 通話とビデオの受信とビデオの実行が可能になります。 WiFi 使用の設定は、ユーザーのデバイスが携帯電話のデータネットワーク経由で WiFi ネットワークを使用する必要があるかどうかを定義します。

既定では、モビリティ、勤務先からの通話、VoIP とビデオの機能が有効になっています。 VoIp およびビデオに WiFi を必須にする設定は無効になっています。 管理者は、コマンドレットを実行することで、これらの機能にアクセスできるユーザーを確認できます。 オプションは、グローバル、サイト、またはユーザーごとにオフにすることができます。

モバイル機能を使用し、勤務先から通話を発信できるようにするには、次の前提条件を満たしている必要があります。

  - Lync Server 2013 でユーザーを有効にする必要があります。

  - ユーザーはエンタープライズ Voip 用に有効になっている必要があります。

  - ユーザーには、 **EnableMobility**オプションが True に設定されているモビリティーポリシーが割り当てられている必要があります。

ユーザーが職場経由で通話を使用できるようにするには、次の2つの追加の前提条件を満たしている必要があります。

  - ユーザーには、[**電話の同時呼び出しを有効にする**] オプションが選択されているボイスポリシーが割り当てられている必要があります。

  - ユーザーには、 **EnableOutsideVoice**オプションが True に設定されているモビリティーポリシーが割り当てられている必要があります。

<div>


> [!NOTE]  
> エンタープライズ Voip を有効にしていないユーザーは、モバイルデバイスを使用して、Lync のボイスオーバー IP (VoIP) 通話を行うことができます。または、モバイルデバイスで [クリックして参加] リンクを使用して、ユーザーに音声ポリシーの適切なオプションを割り当てると、会議に参加できます。 詳細については、「 <A href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013 のモビリティ要件の定義</A>」を参照してください。



</div>

Lync Server 2013 でユーザーを有効にする方法の詳細については、「 [Lync server 2013 のユーザーアカウントを無効にする、または再度有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。 エンタープライズ Voip のユーザーを有効にする方法について詳しくは、「 [Lync Server 2013 でエンタープライズ voip のユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)」をご覧ください。 ボイスポリシーオプションの設定の詳細については、「 [Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)する」を参照してください。

<div>

## <a name="to-modify-global-mobility-policy"></a>グローバルモビリティポリシーを変更するには

1.  Lync Server 管理シェルと Ocscore が CsAdministrator ロールのメンバーとしてインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  モバイル機能へのアクセスをオフにして、世界中の勤務先から通話を発信します。 コマンド ラインで次を入力します。
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > 「モビリティーへのアクセスをオフにする」をオフにすると、勤務先から通話をオフにすることができます。 ただし、勤務先からの通話をオフにすることなく、モバイル機能をオフにすることはできません。

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>サイトによってモビリティポリシーを変更するには

1.  Lync Server 管理シェルと Ocscore が CsAdministrator ロールのメンバーとしてインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  サイトレベルのポリシーを作成し、VoIP およびビデオをオフにして、[IP オーディオと IP ビデオに WiFi を必須にする] を有効にします。 コマンド ラインで次を入力します。
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>ユーザーによるモビリティポリシーの変更

1.  Lync Server 管理シェルと Ocscore が CsAdministrator ロールのメンバーとしてインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  ユーザーレベルのモバイル処理ポリシーを作成し、機動性をオフにして、ユーザーによる勤務先から通話を発信します。 コマンド ラインで次を入力します。
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    「モビリティーへのアクセスをオフにする」をオフにすると、勤務先から通話をオフにすることができます。 ただし、勤務先からの通話をオフにすることなく、モバイル機能をオフにすることはできません。
    
    次に例を示します。
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のユーザーアカウントを無効にするか、再び有効にする](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Lync Server 2013 でのエンタープライズ Voip のユーザーの有効化](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成する](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Lync Server 2013 でのモビリティの要件の定義](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

