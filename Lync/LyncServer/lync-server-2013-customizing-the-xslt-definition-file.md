---
title: 'Lync Server 2013: XSLT 定義ファイルのカスタマイズ'
description: 'Lync Server 2013: XSLT 定義ファイルのカスタマイズ。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing the XSLT definition file
ms:assetid: f18dd78c-3598-4f38-b496-96b750c6e518
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679898(v=OCS.15)
ms:contentKeyID: 49557733
ms.date: 09/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b248b44c9257fa9f30cc99a3773abf71ddbd8651
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553803"
---
# <a name="customizing-the-xslt-definition-file-in-lync-server-2013"></a><span data-ttu-id="e1b3b-103">Lync Server 2013 での XSLT 定義ファイルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="e1b3b-103">Customizing the XSLT definition file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1b3b-104">_**トピックの最終更新日:** 2014-09-11_</span><span class="sxs-lookup"><span data-stu-id="e1b3b-104">_**Topic Last Modified:** 2014-09-11_</span></span>

<span data-ttu-id="e1b3b-105">コンプライアンスサービスは、参加者がいる場合を含め、各 Lync Server 2013、常設チャットサーバーの会話に関連するデータを記録およびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-105">The Compliance service records and archives data related to each Lync Server 2013, Persistent Chat Server conversation, including when a participant:</span></span>

  - <span data-ttu-id="e1b3b-106">常設チャットルームへの参加</span><span class="sxs-lookup"><span data-stu-id="e1b3b-106">Joins a Persistent Chat room</span></span>

  - <span data-ttu-id="e1b3b-107">チャット ルームから退出する</span><span class="sxs-lookup"><span data-stu-id="e1b3b-107">Leaves a chat room</span></span>

  - <span data-ttu-id="e1b3b-108">メッセージを投稿する</span><span class="sxs-lookup"><span data-stu-id="e1b3b-108">Posts a message</span></span>

  - <span data-ttu-id="e1b3b-109">チャット履歴を表示する</span><span class="sxs-lookup"><span data-stu-id="e1b3b-109">Views chat history</span></span>

  - <span data-ttu-id="e1b3b-110">ファイルをアップロードする</span><span class="sxs-lookup"><span data-stu-id="e1b3b-110">Uploads a file</span></span>

  - <span data-ttu-id="e1b3b-111">ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e1b3b-111">Downloads a file</span></span>

<span data-ttu-id="e1b3b-p101">データは XML として送信されるため、XSLT 定義ファイルを使用して組織に最適な書式に変換できます。このトピックでは、コンプライアンス サービスが作成する XML ファイルについて説明します。また、XSLT の定義および出力ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-p101">The data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>

<div>

## <a name="output-format"></a><span data-ttu-id="e1b3b-115">出力書式</span><span class="sxs-lookup"><span data-stu-id="e1b3b-115">Output Format</span></span>

<span data-ttu-id="e1b3b-116">コンプライアンス サービスの出力は、会話 (Conversation 要素) とメッセージ (Messages 要素) によって分類されます。次のコード サンプルに例を示します。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-116">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample.</span></span>

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

<span data-ttu-id="e1b3b-p102">Conversation 要素には、4 つの要素 (Channel、FirstMessage、StartTimeUTC、および EndTimeUTC) が含まれます。Channel 要素には、チャット ルームの Uniform Resource Identifier (URI) が含まれます。FirstMessage 要素は、Messages 要素の最初のメッセージを記述します。StartTimeUTC および EndTimeUTC 要素は、会話の開始および終了時刻を示します。次のコード サンプルに例を示します。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-p102">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample.</span></span>

    <<FirstMessage type="JOIN" content="" id="0">
          <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
          <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    </FirstMessage>

<span data-ttu-id="e1b3b-p103">Message 要素には、2 つの要素 (Sender および DateTimeUTC) と 3 つの属性 (type、content、および id) が含まれます。Sender 要素は、メッセージを送信したユーザーを表し、DateTimeUTC 要素は、イベントの発生時刻を表します。次のコード サンプルに例を示します。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-p103">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample.</span></span>

    <Message type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
    </Message>

<span data-ttu-id="e1b3b-122">次の表では、メッセージ属性 Type、Content、および ID について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-122">The following table describes the message attributes Type, Content, and ID.</span></span>

### <a name="messages-element-attributes"></a><span data-ttu-id="e1b3b-123">Messages 要素の属性</span><span class="sxs-lookup"><span data-stu-id="e1b3b-123">Messages Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1b3b-124">属性</span><span class="sxs-lookup"><span data-stu-id="e1b3b-124">Attribute</span></span></th>
<th><span data-ttu-id="e1b3b-125">説明</span><span class="sxs-lookup"><span data-stu-id="e1b3b-125">Description</span></span></th>
<th><span data-ttu-id="e1b3b-126">省略可能/必須</span><span class="sxs-lookup"><span data-stu-id="e1b3b-126">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b3b-127">型</span><span class="sxs-lookup"><span data-stu-id="e1b3b-127">Type</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-p104">メッセージの型を指定します。メッセージの型については、「Messages 要素のメッセージ型」の表で説明されています。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-p104">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-130">必須</span><span class="sxs-lookup"><span data-stu-id="e1b3b-130">Required</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b3b-131">コンテンツ</span><span class="sxs-lookup"><span data-stu-id="e1b3b-131">Content</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-p105">メッセージの内容が含まれます。Type が Join または Part であるメッセージはこの属性を使用しません。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-p105">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-134">省略可能</span><span class="sxs-lookup"><span data-stu-id="e1b3b-134">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b3b-135">ID</span><span class="sxs-lookup"><span data-stu-id="e1b3b-135">ID</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-p106">コンテンツの一意の ID を指定します。この属性は、Type が Chat であるメッセージでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-p106">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-138">省略可能</span><span class="sxs-lookup"><span data-stu-id="e1b3b-138">Optional</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e1b3b-p107">各 Sender 要素には、5 つの属性 (Username、ID、Email、Internal、および Uri) が含まれます。これらの属性については、次の表で説明されています。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-p107">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

### <a name="sender-element-attributes"></a><span data-ttu-id="e1b3b-141">Sender 要素の属性</span><span class="sxs-lookup"><span data-stu-id="e1b3b-141">Sender Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1b3b-142">属性</span><span class="sxs-lookup"><span data-stu-id="e1b3b-142">Attribute</span></span></th>
<th><span data-ttu-id="e1b3b-143">説明</span><span class="sxs-lookup"><span data-stu-id="e1b3b-143">Description</span></span></th>
<th><span data-ttu-id="e1b3b-144">省略可能/必須</span><span class="sxs-lookup"><span data-stu-id="e1b3b-144">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b3b-145">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="e1b3b-145">Username</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-146">送信者の名前。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-146">The name of the sender.</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-147">省略可能</span><span class="sxs-lookup"><span data-stu-id="e1b3b-147">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b3b-148">ID</span><span class="sxs-lookup"><span data-stu-id="e1b3b-148">ID</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-149">送信者の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-149">The sender’s unique ID.</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-150">必須</span><span class="sxs-lookup"><span data-stu-id="e1b3b-150">Required</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b3b-151">メール</span><span class="sxs-lookup"><span data-stu-id="e1b3b-151">Email</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-152">送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-152">The sender’s email address.</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-153">省略可能</span><span class="sxs-lookup"><span data-stu-id="e1b3b-153">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b3b-154">内部</span><span class="sxs-lookup"><span data-stu-id="e1b3b-154">Internal</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-p108">ユーザーが内部ユーザーとフェデレーション ユーザーのどちらであるかを決定します。この値が True に設定されている場合、ユーザーは内部ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-p108">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-157">省略可能</span><span class="sxs-lookup"><span data-stu-id="e1b3b-157">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b3b-158">Uri</span><span class="sxs-lookup"><span data-stu-id="e1b3b-158">Uri</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-159">ユーザーの SIP URI。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-159">The user’s SIP URI.</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-160">必須</span><span class="sxs-lookup"><span data-stu-id="e1b3b-160">Required</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e1b3b-p109">次の表では、Messages 要素に含めることのできるメッセージ型について説明します。また、各要素の使用方法の例を提供します。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-p109">The following table describes the message types that the Messages element can contain. It also provides examples of how each element is used.</span></span>

### <a name="message-element-message-types"></a><span data-ttu-id="e1b3b-163">Messages 要素のメッセージ型</span><span class="sxs-lookup"><span data-stu-id="e1b3b-163">Message Element Message Types</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1b3b-164">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="e1b3b-164">Message Type</span></span></th>
<th><span data-ttu-id="e1b3b-165">説明</span><span class="sxs-lookup"><span data-stu-id="e1b3b-165">Description</span></span></th>
<th><span data-ttu-id="e1b3b-166">コード例</span><span class="sxs-lookup"><span data-stu-id="e1b3b-166">Code example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1b3b-167">参加</span><span class="sxs-lookup"><span data-stu-id="e1b3b-167">Join</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-168">ユーザーがチャット ルームに参加しました。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-168">A user joins a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;JOIN&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206211842612&quot; string=&quot;2008-03-22T18:50:42.6127374Z&quot; long=&quot;633418086426127374&quot; /&gt; 
&lt;/Message</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b3b-169">パーツ</span><span class="sxs-lookup"><span data-stu-id="e1b3b-169">Part</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-170">ユーザーがチャット ルームから退出しました。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-170">A user leaves a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;PART&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt; Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212610602532&quot; string=&quot;2008-06-04T20:16:42.5324614Z&quot; long=&quot;633482074025324614&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b3b-171">チャット</span><span class="sxs-lookup"><span data-stu-id="e1b3b-171">Chat</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-172">送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-172">The sender’s email address.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;CHAT&quot; content=&quot;hello&quot; id=&quot;1&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351800522&quot; string=&quot;2008-03-12T19:56:40.522264Z&quot; long=&quot;633409486005222640&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b3b-173">バックチャット</span><span class="sxs-lookup"><span data-stu-id="e1b3b-173">Backchat</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-174">ユーザーがチャット履歴の内容を要求しました。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-174">A user requests content from chat history.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;BACKCHAT&quot; content=&quot;backchatcontent&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206034385284&quot; string=&quot;2008-03-20T17:33:05.2841594Z&quot; long=&quot;633416311852841594&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1b3b-175">File upload</span><span class="sxs-lookup"><span data-stu-id="e1b3b-175">File upload</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-176">ユーザーがファイルをアップロードしました。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-176">A user uploads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEUPLOAD&quot; content=&quot;0988239a-bb66-4616-90a4-b07771a2097c.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351828975&quot; string=&quot;2008-03-12T19:57:08.9755711Z&quot; long=&quot;633409486289755711&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1b3b-177">File download</span><span class="sxs-lookup"><span data-stu-id="e1b3b-177">File download</span></span></p></td>
<td><p><span data-ttu-id="e1b3b-178">ユーザーがファイルをダウンロードしました。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-178">A user downloads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEDOWNLOAD&quot; content=&quot;006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;kazuto@litwareinc.com&quot; id=&quot;10&quot; email=&quot;&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212611141851&quot; string=&quot;2008-06-04T20:25:41.8518646Z&quot; long=&quot;633482079418518646&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="e1b3b-179">既定の常設チャット出力 XSD とサンプルの XSL 変換</span><span class="sxs-lookup"><span data-stu-id="e1b3b-179">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="e1b3b-180">次のコード サンプルには、コンプライアンス サーバーからの既定の出力が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-180">The following code sample contains the default output from the Compliance Server.</span></span>

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

<span data-ttu-id="e1b3b-181">次のコード サンプルには、サンプル XSL 変換が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1b3b-181">The following code sample contains a sample XSL transform.</span></span>

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

