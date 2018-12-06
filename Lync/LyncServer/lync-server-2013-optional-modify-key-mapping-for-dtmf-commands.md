---
title: 'Lync Server 2013: (オプション) DTMF コマンドの主要なマッピングを変更する'
TOCTitle: (オプション) DTMF コマンドの主要なマッピングを変更する
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48273790
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (オプション) Lync Server 2013 で DTMF コマンドの主要なマッピングを変更する

 

_**トピックの最終更新日:** 2012-09-30_

ダイヤルイン会議のユーザーは、電話キーパッドのキーを押して、デュアルトーン多重周波数 (DTMF) のコマンドを実行できます。DTMF コマンドを使用すると、会議にダイヤルインするユーザーは、電話のキーパッドを使用して会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。コマンドレットを使用して、DTMF コマンドに使用されるキーを変更できます。このステップはオプションです。

> [!NOTE]
> これらのコマンドレットと使用可能な DTMF オプションの詳細については、「Lync Server 管理シェル」のドキュメントか、 Lync Server 管理シェルのコマンド ライン ヘルプを参照してください。


## DTMF コマンドのキー マッピングを変更するには

1.  コンピューターに **RTCUniversalServerAdmins** グループのメンバーとしてログオンするか、 **Cs-ServerAdministrator** または **CsAdministrator** 役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialinConferencingDtmfConfiguration
    
    このコマンドレットを実行すると、ダイヤルイン会議に使用される DTMF 設定が戻されます。

4.  次のコマンドレットを実行し、変更対象である各オプションで押されるキーを指定します。
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    このコマンドレットを実行すると、ダイヤルイン会議に使用される DTMF 設定が変更されます。
    
    次に例を示します。
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    この例では、アナウンスを有効/無効にするために押されるキーと、全参加者のミュート/ミュート解除のために押されるキーを交換します。ID が指定されていないため、これらの変更はグローバル DTMF 設定に適用されます。

5.  (オプション) 特定サイトに対する DTMF コマンドの追加セットを作成するには、サイト ID と **New-CsDialinConferencingDtmfConfiguration** コマンドレットを使用します。サイトの新たな DTMF 設定を作成すると、そのサイト設定はグローバル設定よりも優先されるようになります。詳細については、「Lync Server 管理シェル」のドキュメントか、 Lync Server 管理シェルのコマンド ライン ヘルプを参照してください。

