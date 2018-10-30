---
title: 会議デバイス情報の表示
TOCTitle: 会議デバイス情報の表示
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994043(v=OCS.15)
ms:contentKeyID: 52056641
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議デバイス情報の表示

 

_**トピックの最終更新日:** 2013-02-20_

Windows PowerShell と **Get-CsMeetingRoom** コマンドレットを使用して、組織で使用するよう構成された会議デバイスの情報を表示できます。Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから **Get-CsMeetingRoom** コマンドレットを実行します。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。


なにもパラメーターを指定せずに **Get-CsMeetingRoom** コマンドレットを使用した場合、すべての会議デバイスの情報を戻します。オプションのパラメーターを指定すると、さまざまな方法で情報をフィルター処理できます。詳細は、「[Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom)」のパラメーターのセクションを参照してください。


## すべての会議デバイスについての情報を表示する

  - すべての会議デバイスの詳細を表示するには、Lync Server 管理シェルに次のコマンドを入力し、Enter キーを押します。
    
        Get-CsMeetingRoom
    
    このコマンドレットは、会議デバイスごとに次のような情報を戻します。この例は、このコマンドレットを実行するときの一部の情報のみを示すことに注意してください。
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

## 特定の会議デバイスについての情報を表示する

  - 特定の会議デバイスの情報を表示するには、Identity パラメーターの前に会議デバイス ID (一般的には、Active Directory 表示名) を指定します。たとえば、次のようになります。
    
        Get-CsMeetingRoom -Identity "Room 1219"

詳細については、[Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom) コマンドレットに関するヘルプ トピックを参照してください。

