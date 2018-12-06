---
title: 信頼されたアプリケーション情報の表示
TOCTitle: 信頼されたアプリケーション情報の表示
ms:assetid: 7b916323-96fb-4308-bc95-c178de41a3d3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688103(v=OCS.15)
ms:contentKeyID: 49887013
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 信頼されたアプリケーション情報の表示

 

_**トピックの最終更新日:** 2015-03-30_

Lync Server 2013 管理シェルで信頼されたアプリケーションの情報を Lync Server 管理シェルで表示するには、以下の手順を使用します。

## Lync Server 管理シェル コマンドレットを使用した、信頼されたアプリケーションの情報の表示

Lync Server 管理シェルと **Get-CsTrustedApplication** コマンドレットを使用して、信頼されたアプリケーションについての情報を表示できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 信頼されたアプリケーションを表示するには

  - 信頼されたアプリケーションをすべて表示するには、Lync Server 管理シェルで次のコマンドを入力して、Enter キーを押します。
    
        Get-CsConferenceDisclaimer
    
    このコマンドは、信頼されたアプリケーションごとに次のような情報を戻します。
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True

詳細については、「[Get-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrustedApplication)」を参照してください。

