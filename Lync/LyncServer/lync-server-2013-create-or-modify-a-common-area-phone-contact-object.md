---
title: 共有エリアの電話の連絡先オブジェクトを作成または変更する
TOCTitle: 共有エリアの電話の連絡先オブジェクトを作成または変更する
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994083(v=OCS.15)
ms:contentKeyID: 52056743
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 共有エリアの電話の連絡先オブジェクトを作成または変更する

 

_**トピックの最終更新日:** 2013-02-20_

共有エリアの電話すべての Active Directory ドメイン サービス 連絡先オブジェクトを作成するには、**New-CsCommonAreaPhone** コマンドレットを使用します。このコマンドレットでは、共有エリアの電話で使用する新しい連絡先オブジェクトを作成するか、既存の連絡先オブジェクトを新しい共有エリアの電話に関連付けることができます。共有エリアの電話に関連付けられている連絡先オブジェクトのプロパティを変更するには、**Set-CsCommonAreaPhone** コマンドレットを使用します。**Set-CsCommonAreaPhone** のオプション パラメーターでは、連絡先の Active Directory 表示名、電話に関連付けられている回線の Uniform Resource Identifier (URI) など、項目を変更できます。また、Lync Server で使用するアカウントの有効化/無効化も行えます。実行できるすべての変更の詳細については、「[Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone)」のパラメーターに関するセクションを参照してください。**New-CsCommonAreaPhone** のパラメーターの詳細については、「[New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone)」を参照してください。

これらの 2 つのコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShell のリモート セッションから実行することもできます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。


## 共有エリアの電話の連絡先オブジェクトを作成する

  - 新しい共有エリアの電話の連絡先オブジェクトを作成するには、**New-CsCommonAreaPhone** コマンドレットを使用します。連絡先オブジェクトを作成する場合は、少なくとも次の情報を指定する必要があります。
    
      - **LineUri**: 共有エリアの電話に割り当てられている電話番号。電話番号を指定する場合は E.164 形式を使用する必要があります。
    
      - **RegistrarPool**: 連絡先オブジェクトを置くレジストラー プールの完全修飾ドメイン名 (FQDN)。
    
      - **OU**: 連絡先オブジェクトを作成する Active Directory コンテナーの識別名。
    
    また、Active Directory ドメイン サービス 表示名を指定することもおすすめします。これを指定しない場合は、GUID を使用して電話の Identity を指定する必要があります。たとえば、次のようになります。
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

## 共有エリアの電話の連絡先オブジェクトを変更する

  - 既存の共有エリアの電話のプロパティを変更するには、連絡先オブジェクトで **Set-CsCommonAreaPhone** コマンドレットを使用します。たとえば、このコマンドでは、DisplayName が Lobby である共有エリアの電話の SIP アドレスを構成します。
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

詳細については、[New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone) コマンドレットおよび [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone) コマンドレットに関するヘルプ トピックを参照してください。

