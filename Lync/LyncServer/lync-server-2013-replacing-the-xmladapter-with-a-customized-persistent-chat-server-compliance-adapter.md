---
title: 'Lync Server 2013: カスタマイズされた常設チャットサーバーコンプライアンスアダプターを使用して XmlAdapter を置き換える'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c90452edc96a424111fcaa8c99dcf60e55e0109
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536354"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Lync Server 2013 で、カスタマイズされた常設チャットサーバーコンプライアンスアダプターに XmlAdapter を置き換える

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

常設チャットサーバーと共にインストールされる XmlAdapter を使用する代わりに、カスタムアダプターを作成することができます。 カスタム アダプターを記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。 このアセンブリは、常設チャットサーバープールの各サーバーの常設チャットサーバーのインストールフォルダーに配置する必要があります。 任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>IComplianceAdapter インターフェイスの実装

このインターフェイスは、名前空間の Compliance.dll アセンブリで定義されてい `Microsoft.Rtc.Internal.Chat.Server.Compliance` ます。 このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。

    void SetConfig(AdapterConfig config)

常設チャットコンプライアンスサーバーは、アダプターが最初に読み込まれたときにこのメソッドを呼び出します。 には、 `AdapterConfig` コンプライアンスアダプターに関連する常設チャットのコンプライアンス構成が含まれています。

    void Translate(ConversationCollection conversations)

常設チャットコンプライアンスサーバーは、翻訳する新しいデータがある限り、定期的な間隔でこのメソッドを呼び出します。 この時間間隔は、 `RunInterval` 常設チャットのコンプライアンス構成で設定されたと同じです。

には、 `ConversationCollection` このメソッドが最後に呼び出されたときに収集された会話情報が含まれています。

</div>

</div>

<span> </span>

</div>

</div>

</div>

