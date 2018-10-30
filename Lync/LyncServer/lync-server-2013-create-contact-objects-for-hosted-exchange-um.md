---
title: 'Lync Server 2013: Hosted Exchange UM の連絡先オブジェクトの作成'
TOCTitle: Hosted Exchange UM の連絡先オブジェクトの作成
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48273160
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Hosted Exchange UM の連絡先オブジェクトの作成

 

_**トピックの最終更新日:** 2012-09-24_

次の手順では、Hosted Exchange ユニファイド メッセージング (UM) の自動応答 (AA) またはサブスクライバー アクセス (SA) の連絡先オブジェクトを作成する方法について説明します。

詳細については、「計画」のドキュメントの「[Lync Server 2013 の Hosted Exchange 連絡先オブジェクト管理](lync-server-2013-hosted-exchange-contact-object-management.md)」を参照してください。

連絡先オブジェクトの構成の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - [New-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExUmContact)


> [!IMPORTANT]
> Lync Server 2013 の連絡先オブジェクトを Hosted Exchange UM に対して有効化する前に、連絡先オブジェクトに適用されるホスト ボイス メール ポリシーを展開する必要があります。詳細については、「<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイス メール ポリシー</A>」を参照してください。



## Hosted Exchange UM の AA または SA の連絡先オブジェクトを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  New-CsExUmContact コマンドレットを実行して、展開に必要な連絡先オブジェクトを作成します。たとえば、AA および SA の連絡先オブジェクトを作成するには、次のように実行します。
    
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True

       &nbsp;
    
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
    
    これらの例は、次のパラメーターを設定します。
    
      - **SipAddress** は、連絡先オブジェクトの SIP アドレスを指定します。これは、Active Directory ドメイン サービスでユーザーまたは連絡先オブジェクトを構成するために以前使用したことのないアドレスである必要があります。この値は、前の例で示したように、"sip:\< *SIP address* \>" の形式にする必要があります。
    
      - **RegistrarPool** は、レジストラー サービスが実行されているプールの完全修飾ドメイン名 (FQDN) を指定します。
        
        > [!NOTE]  
        > Exchange UM の連絡先オブジェクトは、 Lync Server 2013 の前に、 Lync Server 2013 の展開の一部であるプールに移動することはできません。
    
      - **OU** は、この連絡先オブジェクトの配置先となる Active Directory 組織単位を指定します。
    
      - **DisplayNumber** は、連絡先オブジェクトの電話番号を指定します。各連絡先オブジェクトの電話番号は一意である必要があります。
    
      - **AutoAttendant** は、連絡先オブジェクトを自動応答にするかどうかを指定します。発信者は自動応答の音声案内セットを利用することで、電話システムを通して、希望する相手先に連絡することができます。このパラメーターに **False** (既定値) の値が設定されている場合、それはサブスクライバー アクセスの連絡先オブジェクトです。

