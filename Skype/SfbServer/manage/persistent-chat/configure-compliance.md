---
title: Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: '概要: Skype for Business Server 2015 で常設チャット Server コンプライアンスサービスを構成する方法について説明します。'
ms.openlocfilehash: f25df3e85112f91c1286c0be49c428c364acf018
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887846"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成

**概要:** Skype for Business Server 2015 で常設チャット Server コンプライアンスサービスを構成する方法について説明します。

常設チャットのコンプライアンス機能を使用すると、管理者は永続的なチャットメッセージのアーカイブやアクティビティを管理できます。 コンプライアンスサービスは、参加者がいる場合など、各常設チャットサーバーの会話に関連するデータを記録およびアーカイブします。

- 常設チャットルームに参加する

- チャット ルームから退出する

- メッセージを投稿する

- チャット履歴を表示する

- ファイルをアップロードする

- ファイルをダウンロードする

この情報は、必要に応じてコンプライアンス SQL データベースから取得できます。 

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Windows PowerShell を使用してコンプライアンス サービスを構成する

トポロジ ビルダーを使用してコンプライアンス サービスを有効にすると、**Set-CsPersistenChatComplianceConfiguration** コマンドレットを使用してサービスを構成できます。

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

または

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

次のパラメーターを設定できます。

- AdapterType - アダプターの種類を指定できます。 アダプターはサード パーティ製品であり、コンプライアンス データベースのデータを特定の形式に変換します。 既定では XML です。

- OneChatRoomPerOutputFile-このパラメーターを使用すると、チャットルームごとに個別のレポートを作成することができます。

- AddChatRoomDetails - 有効な場合、各チャット ルームに関する追加の詳細をデータベースに記録します。 この設定によりデータベースのサイズが非常に大きくなることから、既定では無効になっています。

- AddUserDetails - 有効な場合、各チャット ユーザーに関する追加の詳細をデータベースに記録します。 この設定によりデータベースのサイズが非常に大きくなることから、既定では無効になっています。

- Identity - コンプライアンス設定のスコープを、グローバル、サイト、サービスの各レベルなど、特定のコレクションに指定できます。 既定ではグローバル レベルです。 

- RunInterval - サーバーが次のコンプライアンス出力ファイルを生成するまでの期間を指定します (既定では 15 分)。

## <a name="use-a-customized-compliance-adapter"></a>カスタマイズされたコンプライアンス アダプターを使用する

常設チャットサーバーと共にインストールされている XmlAdapter を使う代わりに、カスタムアダプターを作成することができます。 記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。 このアセンブリは、常設チャットサーバープールの各サーバーの常設チャットサーバーのインストールフォルダーに配置する必要があります。 任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。

インターフェイスは、名前空間`Microsoft.Rtc.Internal.Chat.Server.Compliance`の対応する .dll アセンブリで定義されます。 このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。

常設チャットのコンプライアンスサーバーは、アダプターが最初に読み込まれたときに、次のメソッドを呼び出します。 に`AdapterConfig`は、コンプライアンスアダプターに関連する常設チャットのコンプライアンス構成が含まれています。

```cpp
void SetConfig(AdapterConfig config)
```

常設チャットのコンプライアンスサーバーでは、翻訳する新しいデータがある限り、次のメソッドが定期的な間隔で呼び出されます。 この時間間隔は、常設チャット`RunInterval`のコンプライアンス構成で設定された as と同じです。

```cpp
void Translate(ConversationCollection conversations)
```

に`ConversationCollection`は、このメソッドが最後に呼び出されたときから収集されたスレッド情報が含まれています。

## <a name="customize-the-xslt-definition-file"></a>XSLT 定義ファイルをカスタマイズする

コンプライアンス データは XML として送信されるため、XSLT 定義ファイルを使用して組織に最適な書式に変換できます。このトピックでは、コンプライアンス サービスが作成する XML ファイルについて説明します。また、XSLT の定義および出力ファイルを提供します。

### <a name="output-format"></a>出力書式

コンプライアンス サービスの出力は、会話 (Conversation 要素) とメッセージ (Messages 要素) によって分類されます。次のコード サンプルに例を示します。

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

Conversation 要素には、4 つの要素 (Channel、FirstMessage、StartTimeUTC、EndTimeUTC) が含まれます。Channel 要素には、チャット ルームの Uniform Resource Identifier (URI) が含まれます。FirstMessage 要素は、Messages 要素の最初のメッセージを記述します。StartTimeUTC および EndTimeUTC 要素は、会話の開始および終了時刻を示します。次のコード サンプルに例を示します。

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Message 要素には、2 つの要素 (Sender、DateTimeUTC) と 3 つの属性 (Type、Content、ID) が含まれます。Sender 要素はメッセージを送信したユーザーを表し、DateTimeUTC 要素はイベントの発生時刻を表します。次のコード サンプルに例を示します。

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

次の表で、メッセージ属性 Type、Content、ID について説明します。

**Messages 要素の属性**

|**属性**|**説明**|**オプション/必須**|
|:-----|:-----|:-----|
|Type  <br/> |メッセージの型を指定します。メッセージの型については、「Messages 要素のメッセージ型」の表で説明しています。  <br/> |必須  <br/> |
|Content  <br/> |メッセージの内容が含まれます。Type が Join または Part であるメッセージはこの属性を使用しません。  <br/> |省略可能  <br/> |
|ID  <br/> |コンテンツの一意の ID を指定します。この属性は、Type が Chat であるメッセージでのみ使用されます。  <br/> |省略可能  <br/> |

各 Sender 要素には、5 つの属性 (Username、ID、Email、Internal、Uri) が含まれます。次の表で、これらの属性について説明します。

**Sender 要素の属性**

|**属性**|**説明**|**オプション/必須**|
|:-----|:-----|:-----|
|Username  <br/> |送信者の名前。  <br/> |省略可能  <br/> |
|ID  <br/> |送信者の一意の ID。  <br/> |必須  <br/> |
|Email  <br/> |送信者のメールアドレス。  <br/> |省略可能  <br/> |
|Internal  <br/> |ユーザーが内部ユーザーとフェデレーション ユーザーのどちらであるかを指定します。この値が True に設定されている場合、ユーザーは内部ユーザーです。  <br/> |省略可能  <br/> |
|Uri  <br/> |ユーザーの SIP URI。  <br/> |必須  <br/> |

次の例は、Messages 要素に含めることができるメッセージの種類を示しています。 また、各要素の使用方法の例を示します。

参加-ユーザーがチャットルームに参加します。

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

パート-ユーザーがチャットルームから退席します。

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

チャット-送信者のメールアドレス。

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

バックチャット-ユーザーがチャット履歴からコンテンツを要求します。

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

ファイルのアップロード-ユーザーがファイルをアップロードします。

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

ファイルのダウンロード-ユーザーがファイルをダウンロードします。

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>既定の常設チャット出力の XSD とサンプルの XSL 変換

次のコード サンプルに、コンプライアンス サーバーからの既定の出力が含まれています。

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

次のコード サンプルには、サンプル XSL 変換が含まれています。

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
