---
title: 'Lync Server 2013: Hosted Exchange 連絡先オブジェクト管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dae7088982fd3f28ead762c6f50ed4543a5cdef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528194"
---
# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Lync Server 2013 での Hosted Exchange の連絡先オブジェクト管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-25_

横断設置型の展開では、自動応答番号およびサブスクライバー アクセス番号ごとに連絡先オブジェクトを構成する必要があります。

Hosted Exchange UM との統合では、ocsumutil.exe は Active Directory Exchange UM 設定に依存するため、ocsumutil.exe を使用して連絡先オブジェクトを管理することはできません。 クロスプレミスの展開では、Lync Server 2013 と hosted Exchange UM が異なるフォレストにインストールされ、それらの間に信頼はありません。 セキュリティ上の理由から、Lync Server 2013 管理者は、Exchange UM Active Directory 設定に直接アクセスすることはできません。 そのため、Lync server 2013 と hosted Exchange UM サービスの2013両方からアクセスできる *共有 SIP アドレススペース* の連絡先オブジェクトを管理するための別のモデルが提供されています。

<div>

## <a name="hosted-contact-object-workflow"></a>ホスト型連絡先オブジェクトのワークフロー

以下では、Hosted Exchange のテナント管理者と協力して、連絡先オブジェクトを管理するための一般的な手順を示します。

1.  Exchange の管理者が、Exchange UM サブスクライバー アクセス連絡先オブジェクトおよび自動応答連絡先オブジェクトの電話番号を要求します。

2.  Lync Server 2013 管理者は、各電話番号の連絡先オブジェクトを作成し、ホストボイスメールポリシーを各連絡先オブジェクトに割り当てます。

3.  Lync Server 2013 管理者は、Exchange 管理者に電話番号を提供します。

4.  Exchange 管理者は、自動応答およびサブスクライバー アクセス用の該当する Exchange UM ダイヤルプランに電話番号を割り当てます。

<div>


> [!NOTE]  
> オンプレミス展開の場合と同様に、連絡先オブジェクトに対して Lync Server 2013 ダイヤルプランの設定を構成する必要はありません。



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>ホスト型連絡先オブジェクトの構成

<div>


> [!NOTE]  
> ホストされた Exchange UM に対して Lync Server 2013 連絡先オブジェクトを有効にする前に、それらに適用されるホストボイスメールポリシーを展開する必要があります。 ここで展開するポリシーは、有効化する連絡先オブジェクトに適用するのであれば、そのスコープがグローバルなものでも、サイト レベルのものでも、ユーザー単位のものでもかまいません。 詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホストボイスメールポリシー</A>」を参照してください。



</div>

横断型展開でホスト型自動応答およびサブスクライバー アクセス連絡先オブジェクトを構成するには、次の各コマンドレットを使用する必要があります。

  - **New-CsExUmContact** は、ホスト型 UM 用の新しい連絡先オブジェクトを作成します。

  - **Set-CsExUmContact** は、Hosted Exchange UM 用の既存の連絡先オブジェクトを変更します。

次の例では、自動応答連絡先オブジェクトが作成されます。

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

この例では、SIP アドレスが sip:exumaa1@fabrikam.com の、新しい Exchange UM 連絡先オブジェクトが作成されます。 Lync Server 2013 レジストラーサービスが実行されているプールの名前は RedmondPool.litwareinc.com です。 この情報が保存される Active Directory 組織単位は、OU=ExUmContacts,DC=litwareinc,DC=com です。 連絡先オブジェクトの電話番号は、2065554567 です。 オプションの -AutoAttendant $True パラメーターは、このオブジェクトが自動応答連絡先オブジェクトであることを指定しています。 -AutoAttendant パラメーターを False (既定) に設定すると、このオブジェクトがサブスクライバー アクセス連絡先オブジェクトであることが指定されます。

New-CsExUmContact と Set-CsExUmContact のコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

