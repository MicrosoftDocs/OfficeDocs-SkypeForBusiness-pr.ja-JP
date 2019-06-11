---
title: 'Lync Server 2013: XSLT 定義ファイルのカスタマイズ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Customizing the XSLT definition file
ms:assetid: f18dd78c-3598-4f38-b496-96b750c6e518
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679898(v=OCS.15)
ms:contentKeyID: 49557733
ms.date: 09/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e57acbd4cbcd66a3a3371c4ce144fcd2a23bd0ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-the-xslt-definition-file-in-lync-server-2013"></a><span data-ttu-id="9e5b1-102">Lync Server 2013 での XSLT 定義ファイルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="9e5b1-102">Customizing the XSLT definition file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e5b1-103">_**最終更新日:** 2014-09-11_</span><span class="sxs-lookup"><span data-stu-id="9e5b1-103">_**Topic Last Modified:** 2014-09-11_</span></span>

<span data-ttu-id="9e5b1-104">コンプライアンスサービスは、参加者がいる場合など、各 Lync Server 2013 の常設チャットサーバーの会話に関連するデータを記録およびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-104">The Compliance service records and archives data related to each Lync Server 2013, Persistent Chat Server conversation, including when a participant:</span></span>

  - <span data-ttu-id="9e5b1-105">常設チャットルームに参加する</span><span class="sxs-lookup"><span data-stu-id="9e5b1-105">Joins a Persistent Chat room</span></span>

  - <span data-ttu-id="9e5b1-106">チャット ルームから退出する</span><span class="sxs-lookup"><span data-stu-id="9e5b1-106">Leaves a chat room</span></span>

  - <span data-ttu-id="9e5b1-107">メッセージを投稿する</span><span class="sxs-lookup"><span data-stu-id="9e5b1-107">Posts a message</span></span>

  - <span data-ttu-id="9e5b1-108">チャット履歴を表示する</span><span class="sxs-lookup"><span data-stu-id="9e5b1-108">Views chat history</span></span>

  - <span data-ttu-id="9e5b1-109">ファイルをアップロードする</span><span class="sxs-lookup"><span data-stu-id="9e5b1-109">Uploads a file</span></span>

  - <span data-ttu-id="9e5b1-110">ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="9e5b1-110">Downloads a file</span></span>

<span data-ttu-id="9e5b1-111">データは XML として配信され、XSLT 定義ファイルを使用することで、組織に最も適した形式に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-111">The data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="9e5b1-112">このトピックでは、コンプライアンス サービスが作成する XML ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-112">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="9e5b1-113">また、XSLT の定義および出力ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-113">It also provides samples of XSLT definition and output files.</span></span>

<div>

## <a name="output-format"></a><span data-ttu-id="9e5b1-114">出力形式</span><span class="sxs-lookup"><span data-stu-id="9e5b1-114">Output Format</span></span>

<span data-ttu-id="9e5b1-115">コンプライアンスサービスの出力は、次のコードサンプルに示すように、スレッド (スレッド) 別に分類され、次にメッセージ (Messages 要素) によって分類されます。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-115">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample.</span></span>

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

<span data-ttu-id="9e5b1-116">スレッド要素には、4つの要素 (チャネル、FirstMessage、StartTimeUTC、EndTimeUTC) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-116">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="9e5b1-117">チャネル要素にはチャットルームの Uniform Resource Identifier (URI) が含まれ、FirstMessage 要素は Messages 要素の最初のメッセージを記述します。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-117">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="9e5b1-118">StartTimeUTC 要素と EndTimeUTC 要素は、次のコードサンプルに示すように、スレッドの開始時刻と終了時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-118">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample.</span></span>

    <<FirstMessage type="JOIN" content="" id="0">
          <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
          <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    </FirstMessage>

<span data-ttu-id="9e5b1-119">メッセージ要素には、2つの要素 (Sender と DateTimeUTC) と3つの属性 (種類、コンテンツ、ID) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-119">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="9e5b1-120">Sender 要素は、メッセージを送信するユーザーを表し、次のコードサンプルに示すように、イベントが発生すると DateTimeUTC 要素を表します。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-120">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample.</span></span>

    <Message type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
    </Message>

<span data-ttu-id="9e5b1-121">次の表で、メッセージ属性 Type、Content、ID について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-121">The following table describes the message attributes Type, Content, and ID.</span></span>

### <a name="messages-element-attributes"></a><span data-ttu-id="9e5b1-122">Messages 要素の属性</span><span class="sxs-lookup"><span data-stu-id="9e5b1-122">Messages Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e5b1-123">属性</span><span class="sxs-lookup"><span data-stu-id="9e5b1-123">Attribute</span></span></th>
<th><span data-ttu-id="9e5b1-124">説明</span><span class="sxs-lookup"><span data-stu-id="9e5b1-124">Description</span></span></th>
<th><span data-ttu-id="9e5b1-125">オプション/必須</span><span class="sxs-lookup"><span data-stu-id="9e5b1-125">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e5b1-126">Type</span><span class="sxs-lookup"><span data-stu-id="9e5b1-126">Type</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-p104">メッセージの型を指定します。メッセージの型については、「Messages 要素のメッセージ型」の表で説明しています。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-p104">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-129">必須</span><span class="sxs-lookup"><span data-stu-id="9e5b1-129">Required</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e5b1-130">Content</span><span class="sxs-lookup"><span data-stu-id="9e5b1-130">Content</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-p105">メッセージの内容が含まれます。Type が Join または Part であるメッセージはこの属性を使用しません。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-p105">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-133">省略可能</span><span class="sxs-lookup"><span data-stu-id="9e5b1-133">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e5b1-134">ID</span><span class="sxs-lookup"><span data-stu-id="9e5b1-134">ID</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-p106">コンテンツの一意の ID を指定します。この属性は、Type が Chat であるメッセージでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-p106">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-137">省略可能</span><span class="sxs-lookup"><span data-stu-id="9e5b1-137">Optional</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9e5b1-p107">各 Sender 要素には、5 つの属性 (Username、ID、Email、Internal、Uri) が含まれます。次の表で、これらの属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-p107">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

### <a name="sender-element-attributes"></a><span data-ttu-id="9e5b1-140">Sender 要素の属性</span><span class="sxs-lookup"><span data-stu-id="9e5b1-140">Sender Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e5b1-141">属性</span><span class="sxs-lookup"><span data-stu-id="9e5b1-141">Attribute</span></span></th>
<th><span data-ttu-id="9e5b1-142">説明</span><span class="sxs-lookup"><span data-stu-id="9e5b1-142">Description</span></span></th>
<th><span data-ttu-id="9e5b1-143">オプション/必須</span><span class="sxs-lookup"><span data-stu-id="9e5b1-143">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e5b1-144">Username</span><span class="sxs-lookup"><span data-stu-id="9e5b1-144">Username</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-145">送信者の名前。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-145">The name of the sender.</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-146">省略可能</span><span class="sxs-lookup"><span data-stu-id="9e5b1-146">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e5b1-147">ID</span><span class="sxs-lookup"><span data-stu-id="9e5b1-147">ID</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-148">送信者の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-148">The sender’s unique ID.</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-149">必須</span><span class="sxs-lookup"><span data-stu-id="9e5b1-149">Required</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e5b1-150">Email</span><span class="sxs-lookup"><span data-stu-id="9e5b1-150">Email</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-151">送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-151">The sender’s email address.</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-152">省略可能</span><span class="sxs-lookup"><span data-stu-id="9e5b1-152">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e5b1-153">Internal</span><span class="sxs-lookup"><span data-stu-id="9e5b1-153">Internal</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-p108">ユーザーが内部ユーザーとフェデレーション ユーザーのどちらであるかを指定します。この値が True に設定されている場合、ユーザーは内部ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-p108">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-156">省略可能</span><span class="sxs-lookup"><span data-stu-id="9e5b1-156">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e5b1-157">Uri</span><span class="sxs-lookup"><span data-stu-id="9e5b1-157">Uri</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-158">ユーザーの SIP URI。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-158">The user’s SIP URI.</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-159">必須</span><span class="sxs-lookup"><span data-stu-id="9e5b1-159">Required</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9e5b1-p109">次の表で、Messages 要素に含めることのできるメッセージ型について説明します。また、各要素の使用方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-p109">The following table describes the message types that the Messages element can contain. It also provides examples of how each element is used.</span></span>

### <a name="message-element-message-types"></a><span data-ttu-id="9e5b1-162">Messages 要素のメッセージ型</span><span class="sxs-lookup"><span data-stu-id="9e5b1-162">Message Element Message Types</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e5b1-163">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="9e5b1-163">Message Type</span></span></th>
<th><span data-ttu-id="9e5b1-164">説明</span><span class="sxs-lookup"><span data-stu-id="9e5b1-164">Description</span></span></th>
<th><span data-ttu-id="9e5b1-165">コード例</span><span class="sxs-lookup"><span data-stu-id="9e5b1-165">Code example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e5b1-166">Join</span><span class="sxs-lookup"><span data-stu-id="9e5b1-166">Join</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-167">ユーザーがチャット ルームに参加しました。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-167">A user joins a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;JOIN&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206211842612&quot; string=&quot;2008-03-22T18:50:42.6127374Z&quot; long=&quot;633418086426127374&quot; /&gt; 
&lt;/Message</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e5b1-168">Part</span><span class="sxs-lookup"><span data-stu-id="9e5b1-168">Part</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-169">ユーザーがチャット ルームから退出しました。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-169">A user leaves a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;PART&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt; Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212610602532&quot; string=&quot;2008-06-04T20:16:42.5324614Z&quot; long=&quot;633482074025324614&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e5b1-170">Chat</span><span class="sxs-lookup"><span data-stu-id="9e5b1-170">Chat</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-171">送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-171">The sender’s email address.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;CHAT&quot; content=&quot;hello&quot; id=&quot;1&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351800522&quot; string=&quot;2008-03-12T19:56:40.522264Z&quot; long=&quot;633409486005222640&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e5b1-172">Backchat</span><span class="sxs-lookup"><span data-stu-id="9e5b1-172">Backchat</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-173">ユーザーがチャット履歴の内容を要求しました。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-173">A user requests content from chat history.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;BACKCHAT&quot; content=&quot;backchatcontent&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206034385284&quot; string=&quot;2008-03-20T17:33:05.2841594Z&quot; long=&quot;633416311852841594&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e5b1-174">File upload</span><span class="sxs-lookup"><span data-stu-id="9e5b1-174">File upload</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-175">ユーザーがファイルをアップロードしました。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-175">A user uploads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEUPLOAD&quot; content=&quot;0988239a-bb66-4616-90a4-b07771a2097c.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351828975&quot; string=&quot;2008-03-12T19:57:08.9755711Z&quot; long=&quot;633409486289755711&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e5b1-176">File download</span><span class="sxs-lookup"><span data-stu-id="9e5b1-176">File download</span></span></p></td>
<td><p><span data-ttu-id="9e5b1-177">ユーザーがファイルをダウンロードしました。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-177">A user downloads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEDOWNLOAD&quot; content=&quot;006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;kazuto@litwareinc.com&quot; id=&quot;10&quot; email=&quot;&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212611141851&quot; string=&quot;2008-06-04T20:25:41.8518646Z&quot; long=&quot;633482079418518646&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="9e5b1-178">既定の常設チャット出力の XSD とサンプルの XSL 変換</span><span class="sxs-lookup"><span data-stu-id="9e5b1-178">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="9e5b1-179">次のコードサンプルは、コンプライアンスサーバーからの既定の出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-179">The following code sample contains the default output from the Compliance Server.</span></span>

    <?xml version="1.0" encoding="utf-8"?>
    <xs:schema id="Conversations"  xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
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

<span data-ttu-id="9e5b1-180">次のコードサンプルには、サンプルの XSL 変換が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e5b1-180">The following code sample contains a sample XSL transform.</span></span>

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

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

