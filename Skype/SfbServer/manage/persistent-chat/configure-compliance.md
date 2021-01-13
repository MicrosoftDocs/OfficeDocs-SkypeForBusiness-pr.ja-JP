---
title: Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: '概要: Skype for Business Server 2015 で常設チャット サーバー コンプライアンス サービスを構成する方法について学習します。'
ms.openlocfilehash: ee7dbc3ad8e7eedcadcc60850e35b753c5fadb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815067"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="aebb4-103">Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成</span><span class="sxs-lookup"><span data-stu-id="aebb4-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="aebb4-104">**概要:** Skype for Business Server 2015 で常設チャット サーバー コンプライアンス サービスを構成する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="aebb4-105">常設チャットコンプライアンスを使用すると、管理者は常設チャット メッセージとアクティビティのアーカイブを維持できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="aebb4-106">Compliance Service は、参加者が次の場合を含め、各常設チャット サーバーの会話に関連するデータを記録およびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="aebb4-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="aebb4-107">常設チャット ルームに参加する</span><span class="sxs-lookup"><span data-stu-id="aebb4-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="aebb4-108">チャット ルームから退出する</span><span class="sxs-lookup"><span data-stu-id="aebb4-108">Leaves a chat room</span></span>

- <span data-ttu-id="aebb4-109">メッセージを投稿する</span><span class="sxs-lookup"><span data-stu-id="aebb4-109">Posts a message</span></span>

- <span data-ttu-id="aebb4-110">チャット履歴を表示する</span><span class="sxs-lookup"><span data-stu-id="aebb4-110">Views chat history</span></span>

- <span data-ttu-id="aebb4-111">ファイルをアップロードする</span><span class="sxs-lookup"><span data-stu-id="aebb4-111">Uploads a file</span></span>

- <span data-ttu-id="aebb4-112">ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="aebb4-112">Downloads a file</span></span>

<span data-ttu-id="aebb4-113">この情報は、必要に応じてコンプライアンス SQLから取得できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="aebb4-114">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="aebb4-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="aebb4-115">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="aebb4-116">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="aebb4-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="aebb4-117">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="aebb4-118">次のコマンドを使用してコンプライアンス サービスをWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aebb4-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="aebb4-119">トポロジ ビルダーを使用してコンプライアンス サービスを有効にした後 **、Set-CsPersistenChatComplianceConfiguration** コマンドレットを使用してサービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="aebb4-120">または</span><span class="sxs-lookup"><span data-stu-id="aebb4-120">or</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="aebb4-121">次のパラメーターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-121">You can set the following parameters:</span></span>

- <span data-ttu-id="aebb4-122">AdapterType - アダプターの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="aebb4-123">アダプターは、コンプライアンス データベースのデータを特定の形式に変換するサード パーティ製品です。</span><span class="sxs-lookup"><span data-stu-id="aebb4-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="aebb4-124">XML が既定です。</span><span class="sxs-lookup"><span data-stu-id="aebb4-124">XML is the default.</span></span>

- <span data-ttu-id="aebb4-125">OneChatRoomPerOutputFile - このパラメーターを使用すると、チャット ルームごとに個別のレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="aebb4-126">AddChatRoomDetails - 有効な場合、このパラメーターはデータベース内の各チャット ルームに関する追加の詳細を記録します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="aebb4-127">この設定ではデータベースのサイズが大幅に増加する可能性があります。この設定は既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="aebb4-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="aebb4-128">AddUserDetails - このパラメーターを有効にすると、データベース内の各チャット ルーム ユーザーに関する追加の詳細が記録されます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="aebb4-129">この設定ではデータベースのサイズが大幅に増加する可能性があります。この設定は既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="aebb4-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="aebb4-130">Identity - このパラメーターを使用すると、グローバル レベル、サイト レベル、サービス レベルなど、特定のコレクションに対してコンプライアンス設定をスコープ設定できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="aebb4-131">既定値はグローバル レベルです。</span><span class="sxs-lookup"><span data-stu-id="aebb4-131">The default is the global level.</span></span> 

- <span data-ttu-id="aebb4-132">RunInterval - このパラメーターは、サーバーが次のコンプライアンス出力ファイルを作成する時間を指定します (既定値は 15 分です)。</span><span class="sxs-lookup"><span data-stu-id="aebb4-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="aebb4-133">カスタマイズされたコンプライアンス アダプターを使用する</span><span class="sxs-lookup"><span data-stu-id="aebb4-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="aebb4-134">常設チャット サーバーと一緒にインストールされている XmlAdapter を使用する代わりに、カスタム アダプターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="aebb4-135">カスタム アダプターを記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aebb4-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="aebb4-136">このアセンブリは、常設チャット サーバー プール内の各サーバーの常設チャット サーバー インストール フォルダーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aebb4-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="aebb4-137">任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="aebb4-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="aebb4-138">インターフェイスは、名前空間の Compliance.dll アセンブリで定義されます  `Microsoft.Rtc.Internal.Chat.Server.Compliance` 。</span><span class="sxs-lookup"><span data-stu-id="aebb4-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="aebb4-139">このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。</span><span class="sxs-lookup"><span data-stu-id="aebb4-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="aebb4-140">常設チャット コンプライアンス サーバーは、アダプターが最初に読み込まれるときに次のメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="aebb4-141">コンプライアンス  `AdapterConfig` アダプターに関連する常設チャット コンプライアンス構成が含まれている。</span><span class="sxs-lookup"><span data-stu-id="aebb4-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```cpp
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="aebb4-142">常設チャット コンプライアンス サーバーは、変換する新しいデータがある限り、定期的に次のメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="aebb4-143">この時間間隔は、常設チャット コンプライアンス  `RunInterval` 構成で設定されている時間と同じになります。</span><span class="sxs-lookup"><span data-stu-id="aebb4-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```cpp
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="aebb4-144">この  `ConversationCollection` メソッドが最後に呼び出された時点から収集された会話情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="aebb4-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="aebb4-145">XSLT 定義ファイルをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="aebb4-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="aebb4-146">コンプライアンス データは XML として配信され、XSLT 定義ファイルを使用して、組織に最適な形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-146">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="aebb4-147">このトピックでは、コンプライアンス サービスが作成する XML ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-147">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="aebb4-148">また、XSLT の定義および出力ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-148">It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="aebb4-149">出力形式</span><span class="sxs-lookup"><span data-stu-id="aebb4-149">Output format</span></span>

<span data-ttu-id="aebb4-150">コンプライアンス サービスの出力は、次のコード サンプルに示すように、会話 (Conversation 要素) とメッセージ (Messages 要素) に分類されます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

<span data-ttu-id="aebb4-151">Conversation 要素には、4 つの要素 (Channel、FirstMessage、StartTimeUTC、EndTimeUTC) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-151">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="aebb4-152">Channel 要素にはチャット ルームの Uniform Resource Identifier (URI) が含まれます。FirstMessage 要素は Messages 要素の最初のメッセージを記述します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-152">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="aebb4-153">StartTimeUTC 要素と EndTimeUTC 要素は、次のコード サンプルに示すように、会話の開始時間と終了時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-153">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="aebb4-154">Message 要素には、2 つの要素 (Sender と DateTimeUTC) と 3 つの属性 (Type、Content、ID) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-154">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="aebb4-155">Sender 要素はメッセージを送信するユーザーを表し、DateTimeUTC 要素は次のコード サンプルに示すように、イベントが発生する時期を表します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-155">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="aebb4-156">次の表では、メッセージ属性 Type、Content、および ID について説明します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="aebb4-157">**Messages 要素の属性**</span><span class="sxs-lookup"><span data-stu-id="aebb4-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="aebb4-158">**属性**</span><span class="sxs-lookup"><span data-stu-id="aebb4-158">**Attribute**</span></span>|<span data-ttu-id="aebb4-159">**説明**</span><span class="sxs-lookup"><span data-stu-id="aebb4-159">**Description**</span></span>|<span data-ttu-id="aebb4-160">**省略可能/必須**</span><span class="sxs-lookup"><span data-stu-id="aebb4-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aebb4-161">種類</span><span class="sxs-lookup"><span data-stu-id="aebb4-161">Type</span></span>  <br/> |<span data-ttu-id="aebb4-p114">メッセージの型を指定します。メッセージの型については、「Messages 要素のメッセージ型」の表で説明されています。</span><span class="sxs-lookup"><span data-stu-id="aebb4-p114">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="aebb4-164">必須</span><span class="sxs-lookup"><span data-stu-id="aebb4-164">Required</span></span>  <br/> |
|<span data-ttu-id="aebb4-165">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="aebb4-165">Content</span></span>  <br/> |<span data-ttu-id="aebb4-p115">メッセージの内容が含まれます。Type が Join または Part であるメッセージはこの属性を使用しません。</span><span class="sxs-lookup"><span data-stu-id="aebb4-p115">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="aebb4-168">省略可能</span><span class="sxs-lookup"><span data-stu-id="aebb4-168">Optional</span></span>  <br/> |
|<span data-ttu-id="aebb4-169">ID</span><span class="sxs-lookup"><span data-stu-id="aebb4-169">ID</span></span>  <br/> |<span data-ttu-id="aebb4-p116">コンテンツの一意の ID を指定します。この属性は、Type が Chat であるメッセージでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-p116">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="aebb4-172">省略可能</span><span class="sxs-lookup"><span data-stu-id="aebb4-172">Optional</span></span>  <br/> |

<span data-ttu-id="aebb4-p117">各 Sender 要素には、5 つの属性 (Username、ID、Email、Internal、および Uri) が含まれます。これらの属性については、次の表で説明されています。</span><span class="sxs-lookup"><span data-stu-id="aebb4-p117">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

<span data-ttu-id="aebb4-175">**Sender 要素の属性**</span><span class="sxs-lookup"><span data-stu-id="aebb4-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="aebb4-176">**属性**</span><span class="sxs-lookup"><span data-stu-id="aebb4-176">**Attribute**</span></span>|<span data-ttu-id="aebb4-177">**説明**</span><span class="sxs-lookup"><span data-stu-id="aebb4-177">**Description**</span></span>|<span data-ttu-id="aebb4-178">**省略可能/必須**</span><span class="sxs-lookup"><span data-stu-id="aebb4-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aebb4-179">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="aebb4-179">Username</span></span>  <br/> |<span data-ttu-id="aebb4-180">送信者の名前。</span><span class="sxs-lookup"><span data-stu-id="aebb4-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="aebb4-181">省略可能</span><span class="sxs-lookup"><span data-stu-id="aebb4-181">Optional</span></span>  <br/> |
|<span data-ttu-id="aebb4-182">ID</span><span class="sxs-lookup"><span data-stu-id="aebb4-182">ID</span></span>  <br/> |<span data-ttu-id="aebb4-183">送信者の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="aebb4-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="aebb4-184">必須</span><span class="sxs-lookup"><span data-stu-id="aebb4-184">Required</span></span>  <br/> |
|<span data-ttu-id="aebb4-185">メール</span><span class="sxs-lookup"><span data-stu-id="aebb4-185">Email</span></span>  <br/> |<span data-ttu-id="aebb4-186">送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="aebb4-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="aebb4-187">省略可能</span><span class="sxs-lookup"><span data-stu-id="aebb4-187">Optional</span></span>  <br/> |
|<span data-ttu-id="aebb4-188">内部</span><span class="sxs-lookup"><span data-stu-id="aebb4-188">Internal</span></span>  <br/> |<span data-ttu-id="aebb4-p118">ユーザーが内部ユーザーとフェデレーション ユーザーのどちらであるかを決定します。この値が True に設定されている場合、ユーザーは内部ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="aebb4-p118">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="aebb4-191">省略可能</span><span class="sxs-lookup"><span data-stu-id="aebb4-191">Optional</span></span>  <br/> |
|<span data-ttu-id="aebb4-192">Uri</span><span class="sxs-lookup"><span data-stu-id="aebb4-192">Uri</span></span>  <br/> |<span data-ttu-id="aebb4-193">ユーザーの SIP URI。</span><span class="sxs-lookup"><span data-stu-id="aebb4-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="aebb4-194">必須</span><span class="sxs-lookup"><span data-stu-id="aebb4-194">Required</span></span>  <br/> |

<span data-ttu-id="aebb4-195">次の例は、Messages 要素に含め可能なメッセージの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="aebb4-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="aebb4-196">また、各要素の使用方法の例を提供します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="aebb4-197">参加 - ユーザーがチャット ルームに参加します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-197">Join - A user joins a chat room.</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="aebb4-198">パート - ユーザーがチャット ルームを離れる。</span><span class="sxs-lookup"><span data-stu-id="aebb4-198">Part - A user leaves a chat room.</span></span>

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="aebb4-199">チャット - 送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="aebb4-199">Chat - The sender's email address.</span></span>

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="aebb4-200">バックチャット - ユーザーがチャット履歴からコンテンツを要求します。</span><span class="sxs-lookup"><span data-stu-id="aebb4-200">Backchat - A user requests content from chat history.</span></span>

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="aebb4-201">ファイルのアップロード - ユーザーがファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="aebb4-201">File upload - A user uploads a file.</span></span>

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="aebb4-202">ファイルのダウンロード - ユーザーがファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aebb4-202">File download - A user downloads a file.</span></span>

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="aebb4-203">既定の常設チャット出力 XSD と XSL 変換の例</span><span class="sxs-lookup"><span data-stu-id="aebb4-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="aebb4-204">次のコード サンプルには、コンプライアンス サーバーからの既定の出力が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-204">The following code sample contains the default output from the Compliance Server:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="aebb4-205">次のコード サンプルには、サンプル XSL 変換が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aebb4-205">The following code sample contains a sample XSL transform:</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
