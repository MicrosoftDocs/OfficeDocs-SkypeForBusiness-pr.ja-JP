---
title: 'Lync Server 2013: モビリティ ポリシーの構成'
TOCTitle: モビリティ ポリシーの構成
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48272164
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのモビリティ ポリシーの構成

 

_**トピックの最終更新日:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 には、モビリティ機能、\[勤務先から通話\] 機能、ボイス オーバー IP (VoIP) またはビデオを使用するユーザーや、VoIP またはビデオに対して WiFi を必須にするかどうかを決定するモビリティ ポリシーが用意されています。\[勤務先から通話\] 機能では、モバイル ユーザーが携帯電話の番号ではなく、勤務先の電話番号を使用して携帯電話で通話を発信および着信できます。この機能により、相手に発信者の携帯電話番号が表示されるのを防ぎ、発信の電話料金を回避できます。VoIP およびビデオを構成すると、ユーザーが VoIP 通話を発信および着信できるようになります。また、WiFi の使用法の設定では、携帯電話会社の回線経由での WiFi ネットワークの使用をユーザーのデバイスで必須にするかどうかが定義されます。

既定では、モビリティ機能、\[勤務先から通話\] 機能、VoIP およびビデオ機能は有効になっています。VoIP およびビデオで WiFi を必須にする設定は無効になっています。管理者は、コマンドレットを実行して、これらの機能にアクセスできるユーザーを指定できます。オプションは、グローバル、サイト別、またはユーザー別に無効にできます。

モビリティ機能および \[勤務先から通話\] を使用できるためには、ユーザーが次の前提条件を満たしている必要があります。

  - ユーザーは、Lync Server 2013 に対して有効になっている必要があります。

  - ユーザーは、エンタープライズ VoIP に対して有効になっている必要があります。

  - ユーザーには、**EnableMobility** オプションが True に設定されているモビリティ ポリシーが割り当てられている必要があります。

ユーザーが \[勤務先から通話\] を使用できるためには、ユーザーは次の 2 つの追加の前提条件を満たす必要があります。

  - ユーザーには、\[**電話の同時呼び出しを有効にする**\] オプションが選択されている音声ポリシーが割り当てられている必要があります。

  - ユーザーには、**EnableOutsideVoice** オプションが True に設定されているモビリティ ポリシーが割り当てられている必要があります。

> [!NOTE]
> エンタープライズ VoIP に対して有効になっていないユーザーに音声ポリシーの適切なオプションを割り当てると、そのユーザーは、モバイル デバイスを使用して Lync と Lync の間でボイス オーバー IP (VoIP) 通話を行うか、モバイル デバイスで [クリックして参加] リンクを使用してモバイル デバイスから会議に参加できます。詳細については、「<a href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013 でのモビリティの要件の定義</a>」を参照してください。


ユーザーを Lync Server 2013 に対して有効にする方法については、「[Lync Server 2013 ユーザー アカウントの再有効化または無効化](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)」を参照してください。ユーザーを エンタープライズ VoIP に対して有効にする方法については、「[Lync Server 2013 でのエンタープライズ VoIP に対するユーザーの有効化](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。音声ポリシーのオプションを設定する方法については、「[Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)」を参照してください。

## グローバル モビリティ ポリシーを変更するには

1.  Lync Server 管理シェルおよび Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  モビリティおよび \[勤務先から通話\] へのアクセスをグローバルに無効にします。コマンド ラインで、次のように入力します。
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    > [!NOTE]
    > モビリティへのアクセスをオフにしなくても &quot;勤務先から通話&quot; をオフにできます。ただし、モビリティをオフにする場合は、&quot;勤務先から通話&quot; もオフにする必要があります。


## モビリティ ポリシーをサイト別に変更するには

1.  Lync Server 管理シェルおよび Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  サイト レベルのポリシーを作成し、VoIP とビデオを無効にして、IP オーディオと IP ビデオに対して WiFi を必須にする機能をサイト別に有効にします。コマンドラインで、次のように入力します。
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

## モビリティ ポリシーをユーザー別に変更するには

1.  Lync Server 管理シェルおよび Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  ユーザー レベルのモビリティ ポリシーを作成し、モビリティと \[勤務先から通話\] をユーザー別に無効にします。コマンド ラインで、次のように入力します。
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    モビリティへのアクセスをオフにしなくても "勤務先から通話" をオフにできます。ただし、モビリティをオフにする場合は、"勤務先から通話" もオフにする必要があります。
    
    次に例を示します。
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

## 関連項目

#### タスク

[Lync Server 2013 ユーザー アカウントの再有効化または無効化](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Lync Server 2013 でのエンタープライズ VoIP に対するユーザーの有効化](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  

#### 概念

[Lync Server 2013 でのモビリティの要件の定義](lync-server-2013-defining-your-mobility-requirements.md)  

#### その他のリソース

[New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy)

