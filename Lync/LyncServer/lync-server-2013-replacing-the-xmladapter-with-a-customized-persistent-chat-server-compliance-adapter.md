---
title: 'Lync Server 2013: カスタマイズされた常設チャットサーバーコンプライアンスアダプターを使用して XmlAdapter を置き換える'
description: 'Lync Server 2013: カスタマイズされた常設チャットサーバーのコンプライアンスアダプターに XmlAdapter を置き換えます。'
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
ms.openlocfilehash: 3a90b4df7df42ffdc6c55e9b551b0eb53d07ab1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576143"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="34851-103">Lync Server 2013 で、カスタマイズされた常設チャットサーバーコンプライアンスアダプターに XmlAdapter を置き換える</span><span class="sxs-lookup"><span data-stu-id="34851-103">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34851-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="34851-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="34851-105">常設チャットサーバーと共にインストールされる XmlAdapter を使用する代わりに、カスタムアダプターを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="34851-105">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="34851-106">カスタム アダプターを記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34851-106">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="34851-107">このアセンブリは、常設チャットサーバープールの各サーバーの常設チャットサーバーのインストールフォルダーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34851-107">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="34851-108">任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="34851-108">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="34851-109">IComplianceAdapter インターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="34851-109">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="34851-110">このインターフェイスは、名前空間の Compliance.dll アセンブリで定義されてい `Microsoft.Rtc.Internal.Chat.Server.Compliance` ます。</span><span class="sxs-lookup"><span data-stu-id="34851-110">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="34851-111">このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。</span><span class="sxs-lookup"><span data-stu-id="34851-111">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="34851-112">常設チャットコンプライアンスサーバーは、アダプターが最初に読み込まれたときにこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="34851-112">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="34851-113">には、 `AdapterConfig` コンプライアンスアダプターに関連する常設チャットのコンプライアンス構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34851-113">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="34851-114">常設チャットコンプライアンスサーバーは、翻訳する新しいデータがある限り、定期的な間隔でこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="34851-114">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="34851-115">この時間間隔は、 `RunInterval` 常設チャットのコンプライアンス構成で設定されたと同じです。</span><span class="sxs-lookup"><span data-stu-id="34851-115">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="34851-116">には、 `ConversationCollection` このメソッドが最後に呼び出されたときに収集された会話情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34851-116">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

