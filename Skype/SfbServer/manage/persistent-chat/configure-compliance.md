---
title: 2015 年の常設チャット サーバーのコンプライアンス Skype for Business Server構成する
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
description: '概要: 2015 年に常設チャット サーバー コンプライアンス サービスを構成するSkype for Business Serverします。'
ms.openlocfilehash: ff49a32009b60447823675b90ee4b633ff8f0cb7cfdf3529a3afc26f3c067f79
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349309"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>2015 年の常設チャット サーバーのコンプライアンス Skype for Business Server構成する

**概要:** 2015 年に常設チャット サーバー コンプライアンス サービスを構成するSkype for Business Serverします。

常設チャットのコンプライアンスにより、管理者は常設チャット メッセージとアクティビティのアーカイブを維持できます。 コンプライアンス サービスは、参加者を含む、常設チャット サーバーの各会話に関連するデータを記録およびアーカイブします。

- 常設チャット ルームに参加する

- チャット ルームから退出する

- メッセージを投稿する

- チャット履歴を表示する

- ファイルをアップロードする

- ファイルをダウンロードする

この情報は、必要に応じてコンプライアンス SQLデータベースから取得できます。 

> [!NOTE]
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>ポリシーを使用してコンプライアンス サービスを構成Windows PowerShell

トポロジ ビルダーを使用してコンプライアンス サービスを有効にした後 **、Set-CsPersistenChatComplianceConfiguration** コマンドレットを使用してサービスを構成できます。

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

または

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

次のパラメーターを設定できます。

- AdapterType - アダプターの種類を指定できます。 アダプターは、コンプライアンス データベース内のデータを特定の形式に変換するサード パーティ製品です。 XML は既定です。

- OneChatRoomPerOutputFile - このパラメーターを使用すると、チャット ルームごとに個別のレポートを作成できます。

- AddChatRoomDetails - 有効にすると、このパラメーターはデータベース内の各チャット ルームに関する追加の詳細を記録します。 この設定はデータベースのサイズを大幅に増やす可能性があるから、既定では無効になっています。

- AddUserDetails - 有効にすると、このパラメーターはデータベース内の各チャット ルーム ユーザーに関する追加の詳細を記録します。 この設定はデータベースのサイズを大幅に増やす可能性があるから、既定では無効になっています。

- Identity - このパラメーターを使用すると、グローバル レベル、サイト レベル、サービス レベルなど、特定のコレクションのコンプライアンス設定をスコープ設定できます。 既定値はグローバル レベルです。 

- RunInterval - このパラメーターは、サーバーが次のコンプライアンス出力ファイルを作成する時間を指定します (既定値は 15 分です)。

## <a name="use-a-customized-compliance-adapter"></a>カスタマイズされたコンプライアンス アダプターの使用

常設チャット サーバーにインストールされている XmlAdapter を使用する代わりに、カスタム アダプターを記述できます。 カスタム アダプターを記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。 このアセンブリは、常設チャット サーバー プール内の各サーバーの常設チャット サーバー インストール フォルダーに配置する必要があります。 任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。

インターフェイスは、名前空間の Compliance.dllアセンブリで定義されます  `Microsoft.Rtc.Internal.Chat.Server.Compliance` 。 このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。

常設チャット コンプライアンス サーバーは、アダプターが最初に読み込まれるときに、次のメソッドを呼び出します。 コンプライアンス  `AdapterConfig` アダプターに関連する常設チャットコンプライアンス構成が含まれる。

```cpp
void SetConfig(AdapterConfig config)
```

常設チャット コンプライアンス サーバーは、翻訳する新しいデータがある限り、定期的に次のメソッドを呼び出します。 この時間間隔は、常設チャット コンプライアンス  `RunInterval` 構成で設定されている as と等しくなります。

```cpp
void Translate(ConversationCollection conversations)
```

この  `ConversationCollection` メソッドが最後に呼び出された時点から収集された会話情報が含まれる。

## <a name="customize-the-xslt-definition-file"></a>XSLT 定義ファイルをカスタマイズする

コンプライアンス データは XML として配信され、XSLT 定義ファイルを使用して、組織に最適な形式に変換できます。 このトピックでは、コンプライアンス サービスが作成する XML ファイルについて説明します。 また、XSLT の定義および出力ファイルを提供します。

### <a name="output-format"></a>出力形式

コンプライアンス サービスの出力は、次のコード サンプルに示すように、会話 (Conversation 要素) とメッセージ (Message 要素) によって分類されます。

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

Conversation 要素には、チャネル、FirstMessage、StartTimeUTC、EndTimeUTC の 4 つの要素が含まれます。 Channel 要素にはチャット ルームの Uniform Resource IDENTIFIER (URI) が含まれています。FirstMessage 要素は Messages 要素の最初のメッセージを記述します。 StartTimeUTC 要素と EndTimeUTC 要素は、次のコード サンプルに示すように、会話の開始時間と終了時間を提供します。

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Message 要素には、2 つの要素 (Sender と DateTimeUTC) と 3 つの属性 (Type、Content、ID) が含まれます。 Sender 要素はメッセージを送信するユーザーを表し、DateTimeUTC 要素は次のコード サンプルに示すように、イベントが発生した場合を表します。

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

次の表では、メッセージ属性 Type、Content、および ID について説明します。

**Messages 要素の属性**

|**属性**|**説明**|**オプション/必須**|
|:-----|:-----|:-----|
|型  <br/> |メッセージの型を指定します。メッセージの型については、「Messages 要素のメッセージ型」の表で説明されています。  <br/> |必須  <br/> |
|コンテンツ  <br/> |メッセージの内容が含まれます。Type が Join または Part であるメッセージはこの属性を使用しません。  <br/> |省略可能  <br/> |
|ID  <br/> |コンテンツの一意の ID を指定します。この属性は、Type が Chat であるメッセージでのみ使用されます。  <br/> |省略可能  <br/> |

各 Sender 要素には、5 つの属性 (Username、ID、Email、Internal、および Uri) が含まれます。これらの属性については、次の表で説明されています。

**Sender 要素の属性**

|**属性**|**説明**|**オプション/必須**|
|:-----|:-----|:-----|
|Username  <br/> |送信者の名前。  <br/> |省略可能  <br/> |
|ID  <br/> |送信者の一意の ID。  <br/> |必須  <br/> |
|電子メール  <br/> |送信者の電子メール アドレス。  <br/> |省略可能  <br/> |
|内部  <br/> |ユーザーが内部ユーザーとフェデレーション ユーザーのどちらであるかを決定します。この値が True に設定されている場合、ユーザーは内部ユーザーです。  <br/> |省略可能  <br/> |
|Uri  <br/> |ユーザーの SIP URI。  <br/> |必須  <br/> |

次の例は、Messages 要素に含まれるメッセージの種類を示しています。 また、各要素の使用方法の例を提供します。

参加 - ユーザーがチャット ルームに参加します。

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

パート - ユーザーがチャット ルームを離れる。

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

チャット - 送信者の電子メール アドレス。

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat - ユーザーがチャット履歴からコンテンツを要求します。

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

ファイルのアップロード - ユーザーがファイルをアップロードします。

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

ファイルのダウンロード - ユーザーがファイルをダウンロードします。

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>既定の常設チャット出力 XSD と XSL 変換の例

次のコード サンプルには、コンプライアンス サーバーからの既定の出力が含まれます。

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

次のコード サンプルには、XSL 変換のサンプルが含まれます。

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
