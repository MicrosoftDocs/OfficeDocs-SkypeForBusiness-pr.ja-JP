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
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Lync Server 2013 の Hosted Exchange 連絡先オブジェクト管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-25_

クロスプレミスの展開で、自動応答の番号とサブスクライバーのアクセス番号ごとに、連絡先オブジェクトを構成する必要があります。

ホストされた Exchange UM との統合のために、Active Directory の Exchange UM 設定によって異なるため、連絡先オブジェクトを管理するために ocsumutil を使うことはできません。 クロスプレミスの展開では、Lync Server 2013 とホストされた Exchange UM は別々のフォレストにインストールされ、それらの間に信頼はありません。 セキュリティ上の理由から、Lync Server 2013 管理者は Exchange UM Active Directory の設定に直接アクセスすることはできません。 このため、Lync Server 2013 には、Lync Server 2013 とホストされている Exchange UM サービスの両方からアクセスできる*共有 SIP アドレス空間*の連絡先オブジェクトを管理するための別のモデルが用意されています。

<div>

## <a name="hosted-contact-object-workflow"></a>ホステッド連絡先オブジェクトワークフロー

ホストされた Exchange テナント管理者と協力して連絡先オブジェクトを管理する一般的な手順を次に示します。

1.  Exchange 管理者は、Exchange UM サブスクライバーアクセスと自動応答の連絡先オブジェクトの電話番号を要求します。

2.  Lync Server 2013 管理者は、電話番号ごとに連絡先オブジェクトを作成し、ホストされたボイスメールポリシーを各連絡先オブジェクトに割り当てます。

3.  Lync Server 2013 管理者は、Exchange 管理者に電話番号を提供します。

4.  Exchange 管理者は、自動応答と加入者アクセスの適切な Exchange UM ダイヤルプランに電話番号を割り当てます。

<div>


> [!NOTE]  
> オンプレミスの展開があるため、連絡先オブジェクトの Lync Server 2013 ダイヤルプランの設定を構成する必要はありません。



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>ホステッド連絡先オブジェクトの構成

<div>


> [!NOTE]  
> Lync Server 2013 連絡先オブジェクトをホストされた Exchange UM に対して有効にする前に、それらに適用されるホストされたボイスメールポリシーを展開する必要があります。 有効にする連絡先オブジェクトに適用される限り、ポリシーはグローバル、サイトレベル、またはユーザーごとのスコープにすることができます。 詳細については、「 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイスメールポリシー</A>」を参照してください。



</div>

クロスプレミスの展開でホストされた自動応答とサブスクライバーアクセスの連絡先オブジェクトを構成するには、次のコマンドレットを使用する必要があります。

  - **新しい-CsExUmContact**は、ホストされた UM 用の新しい連絡先オブジェクトを作成します。

  - **Set-CsExUmContact**は、ホストされた Exchange UM の既存の連絡先オブジェクトを変更します。

次の例では、自動応答の連絡先オブジェクトを作成します。

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

この例では、SIP アドレス sip:exumaa1@fabrikam.com を使用して、新しい Exchange UM 連絡先オブジェクトを作成します。 Lync Server 2013 レジストラーサービスを実行しているプールの名前は、RedmondPool.litwareinc.com です。 この情報が保存される Active Directory の組織単位は、OU = ExUmContacts、DC = litwareinc、DC = com です。 連絡先オブジェクトの電話番号は2065554567です。 オプション-AutoAttendant $True パラメーターは、このオブジェクトが自動応答の連絡先オブジェクトであることを指定します。 -AutoAttendant パラメーターを False に設定する (既定) サブスクライバーアクセスの連絡先オブジェクトを指定します。

新しい-CsExUmContact と Set-CsExUmContact コマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

