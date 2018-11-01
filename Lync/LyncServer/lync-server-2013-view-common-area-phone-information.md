---
title: 共通領域電話情報を表示する
TOCTitle: 共通領域電話情報を表示する
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994081(v=OCS.15)
ms:contentKeyID: 52056737
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 共通領域電話情報を表示する

 

_**トピックの最終更新日:** 2013-02-20_

**Get-CsCommonAreaPhone** コマンドレットを使用して、組織で使用するよう構成された共通領域電話についての情報を表示できます。パラメーターを指定せずにこのコマンドレットを呼び出すと、すべての共通領域電話に関する情報が返されます。オプションのパラメーターを指定すると、さまざまな方法で情報をフィルター処理できます。たとえば、指定した組織単位 (OU) 内の連絡先オブジェクトを持つすべての共通領域電話や、指定した建物にあるすべての連絡先オブジェクトを返すことができます。**Get-CsCommonAreaPhone** パラメーターについての詳細は、「[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)」を参照してください。

Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから **Get-CsCommonAreaPhone** コマンドレットを実行します。


## すべての共通領域電話についての情報を表示する

  - すべての共通領域電話に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsCommonAreaPhone
    
    次のような情報が表示されます。
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

詳細については、[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone) コマンドレットに関するヘルプ トピックを参照してください。

