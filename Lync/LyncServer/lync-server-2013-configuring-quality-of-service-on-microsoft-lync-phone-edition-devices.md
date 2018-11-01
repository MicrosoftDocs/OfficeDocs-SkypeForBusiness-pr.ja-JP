---
title: Microsoft Lync Phone Edition デバイスにおけるサービスの品質  (QoS) の構成
TOCTitle: Microsoft Lync Phone Edition デバイスにおけるサービスの品質  (QoS) の構成
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48273199
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Lync Phone Edition デバイスにおけるサービスの品質 (QoS) の構成

 

_**トピックの最終更新日:** 2012-11-01_

サービスの品質 (QoS) は、iPhone などのデバイスでは既定で有効になりませんが、Lync Phone Edition を実行しているデバイス (一般に UC (統合コミュニケーション) 電話と呼ばれます) では既定で有効になります。これを確認するには、Lync Server 管理シェルで次の Windows PowerShell コマンドを実行します。

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

これらのプロパティのうち、サービスの品質に関連するのは VoiceDiffServTag だけです。VoiceDiffServTag は、Lync Phone Edition デバイスからの音声トラフィックに割り当てられた DSCP 値を表します。

> [!NOTE]
> Voice8021p パラメーターは、Lync Server 2013 ではサポートされなくなりました。Microsoft Lync Server 2010 との下位互換性のためにまだ使用できますが、Lync Server 2013 で使用するデバイスに対しては効果はありません。


ほとんどのネットワークでは、Lync Phone Edition のパケットを VoiceDiffServTag 40 でマーキングしても問題になることはありませんが、この値は、音声トラフィックに対して使用される一般的な値ではありません。音声トラフィックは、ほとんど常に DSCP コード 46 でマーキングされます。ネットワーク全体の一貫性を確保するために、UC 電話の VoiceDiffServTag プロパティを 46 に変更することをお勧めします。

そのためには、Windows PowerShell または Lync Server コントロール パネルを使用します。Windows PowerShell を使用して VoiceDiffServTag の値を変更するには、Lync Server 管理シェルで次のコマンドを実行します。

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

上のコマンドは、UC 電話構成設定のグローバル コレクションを変更します。UC 電話設定は、サイト スコープに割り当てることもできます。UC 電話構成設定をサイト スコープで変更するには、サイト ID を指定する必要があります。次に例を示します。

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

次のコマンドを使用して、すべての UC 電話構成設定を同時に変更することもできます。

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Lync Server コントロール パネルを使用してこの変更を行う場合は、コントロール パネルを起動して、次の手順に従います。

1.  \[**クライアント**\] をクリックして、\[**デバイス構成**\] をクリックします。

2.  \[**デバイス構成**\] タブで、変更する設定のコレクションをダブルクリックします (\[**グローバル**\] など)。

3.  \[**デバイス構成の編集**\] ダイアログ ボックスで、\[**音声のサービス品質 (QoS)**\] ボックスの値を **46** に設定し、\[**確定**\] をクリックします。

複数のコレクションがある場合は、UC 電話設定の各コレクションに対してこのプロセスを繰り返す必要があります。Lync Server コントロール パネルでは、複数の設定コレクションを同時に変更することはできません。

Windows オペレーティング システム ベースではないデバイス (iPhone など) がある場合、VoiceDiffServTag の設定を変更しても、それらのデバイスには影響しません。それらのデバイスの DSCP 値を変更するには、そのデバイスの管理マニュアルを参照する必要があります。

