---
title: 'Lync Server 2013: エッジ サーバー証明書を計画する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 737e0845b4b9966accd8c450b8a300b4f1bb128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Lync Server 2013 でエッジ サーバー証明書を計画する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-05_

Lync Server 2013 で、Edge 用の証明書の作成が簡略化されています。

**エッジ サーバー用の証明書のフロー チャート**

![4364 a5fc20db-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "4364 a5fc20db-b577-6a709a8367cd")

1つの公開証明書を作成して、証明書に対して定義されたエクスポート可能な秘密キーがあることを確認し、証明書ウィザードを使用して、次のエッジサーバーの外部インターフェイスに割り当てます。

<div>


> [!IMPORTANT]  
> Lync Server では、ワイルドカード証明書はサポートされていません。リバースプロキシを介して単純な Url を要約するために使用された場所を除きます。 各 SIP ドメイン名、Web 会議エッジサービス、A/V Edge サービス、および展開によって提供される XMPP ドメインに対して、個別のサブジェクト代替名 (San) を定義する必要があります。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 で導入されました。現在の証明書の有効期限が切れる前に、オーディオ/ビデオ認証の証明書をステージングするには、追加の計画が必要です。 外部 Edge インターフェイスの複数の目的を持つ1つの証明書の代わりに、アクセスエッジサービスと Web 会議エッジサービスに割り当てられている証明書と、A/V Edge サービス用の証明書の2つが必要です。 詳細については、「 <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">Lync Server 2013 での、AV および OAuth 証明書の使用</A>」を参照してください。



</div>

<div>


> [!IMPORTANT]  
> エッジサーバーのプールがある場合は、各エッジサーバーに秘密キーを持つ証明書をエクスポートし、各エッジサーバーサービスに証明書を割り当てます。 内部エッジサーバー証明書についても同じ操作を行い、秘密キーを使って証明書をエクスポートし、各内部エッジインターフェイスに割り当てます。



</div>

  - 証明書に対して、エクスポート可能な秘密キーが割り当てられていることを確認する

  - Access Edge サービス (証明書ウィザードの [**外部 SIP アクセスエッジ**] とも呼ばれます)

  - Web 会議エッジサービス (証明書ウィザードの [**外部] Web 会議エッジ**とも呼ばれます)

  - A/V 認証サービス (証明書ウィザードの「**外部**」とも呼ばれます)

エクスポート可能な秘密キーを使用して、1つの内部証明書を作成し、エッジサーバーの内部インターフェイスごとにコピーして割り当てます。

  - エッジサーバー (証明書ウィザードでは、" **edge** " と呼ばれます)

<div>


> [!IMPORTANT]  
> エッジサーバーサービスごとに個別の証明書を使用することができます。 個別の証明書を選択することをお勧めするのは、A/V Edge サービス証明書の新しいローリング証明書機能を使用する場合です。 この機能を使用する場合は、アクセスエッジサービスおよび Web 会議エッジサービスから A/V Edge サービス証明書を分離することをお勧めします。 各サービスに対して個別の証明書を取得して割り当てる場合は、秘密キーが A/v Edge サービス用にエクスポート可能であることを要求する必要があります (これは、A/v 認証サービスの場合もあります)。また A/V に同じ証明書を割り当てる必要があります。各エッジサーバー上のエッジ外部インターフェイス。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での、AV および OAuth 証明書の使用-セットアップ-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[エッジ サーバーの計画に影響する Lync Server 2013 での変更点](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

