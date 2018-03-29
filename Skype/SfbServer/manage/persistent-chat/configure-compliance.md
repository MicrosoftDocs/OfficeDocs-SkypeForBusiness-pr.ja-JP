---
title: Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: '概要: は、Skype のビジネス サーバー 2015 の永続的なチャット サーバーのコンプライアンス サービスを構成する方法について説明します。'
ms.openlocfilehash: a77b07b0e05a248c351e73c5b8a5f2cebf97236c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーのコンプライアンス サービスの構成
 
**の概要:**ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのコンプライアンス サービスを構成する方法について説明します。
  
永続的なチャットのコンプライアンスでは、管理者の活動だけでなく、永続的なチャット メッセージのアーカイブを維持することができます。 コンプライアンス サービスでは、記録しと関係者を含め、各永続的なチャット サーバーのテーマに関連するデータをアーカイブします。
  
- 永続的なチャット ルームに参加します。
    
- チャット ルームから退出する
    
- メッセージを投稿する
    
- チャット履歴を表示する
    
- ファイルをアップロードする
    
- ファイルをダウンロードする
    
この情報は、必要に応じてコンプライアンス SQL データベースから取得できます。 
  
## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Windows PowerShell を使用してコンプライアンス サービスを構成する

トポロジ ビルダーを使用してコンプライアンス サービスを有効にすると、**Set-CsPersistenChatComplianceConfiguration** コマンドレットを使用してサービスを構成できます。
  
```
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

または
  
```
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

次のパラメーターを設定できます。
  
- AdapterType - アダプターの種類を指定できます。 アダプターはサード パーティ製品であり、コンプライアンス データベースのデータを特定の形式に変換します。 既定では XML です。
    
- OneChatRoomPerOutputFile - このパラメーターを指定できます各チャット ルームの作成するレポートを分割します。
    
- AddChatRoomDetails - 有効な場合、各チャット ルームに関する追加の詳細をデータベースに記録します。 この設定によりデータベースのサイズが非常に大きくなることから、既定では無効になっています。
    
- AddUserDetails - 有効な場合、各チャット ユーザーに関する追加の詳細をデータベースに記録します。 この設定によりデータベースのサイズが非常に大きくなることから、既定では無効になっています。
    
- Identity - コンプライアンス設定のスコープを、グローバル、サイト、サービスの各レベルなど、特定のコレクションに指定できます。 既定ではグローバル レベルです。 
    
- RunInterval - サーバーが次のコンプライアンス出力ファイルを生成するまでの期間を指定します (既定では 15 分)。
    
## <a name="use-a-customized-compliance-adapter"></a>カスタマイズされたコンプライアンス アダプターを使用する

永続的なチャット サーバーにインストールされている XmlAdapter を使用する代わりにカスタム アダプターを記述することができます。 記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。 永続的なチャット サーバー プールの各サーバの永続的なチャット サーバーのインストール フォルダーにこのアセンブリを配置する必要があります。 任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。
  
Compliance.dll アセンブリ、名前空間内でインターフェイスが定義されている`Microsoft.Rtc.Internal.Chat.Server.Compliance`。 このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。
  
永続的なチャット コンプライアンス サーバーは、アダプターが最初に読み込まれたときに、次のメソッドを呼び出します。 `AdapterConfig`準拠のアダプターに関連する永続的なチャット コンプライアンス構成が含まれています。
  
```
void SetConfig(AdapterConfig config)
```

永続的なチャット コンプライアンス サーバーに変換する新しいデータがある限り、定期的に次のメソッドを呼び出します。 この時間間隔は、 `RunInterval` 、永続的なチャットのコンプライアンスの構成で設定されています。
  
```
void Translate(ConversationCollection conversations)
```

`ConversationCollection`このメソッドが呼び出された最後の時間から収集された通信に関する情報が含まれています。
  
## <a name="customize-the-xslt-definition-file"></a>XSLT 定義ファイルをカスタマイズする

コンプライアンス データは XML として送信されるため、XSLT 定義ファイルを使用して組織に最適な書式に変換できます。このトピックでは、コンプライアンス サービスが作成する XML ファイルについて説明します。また、XSLT の定義および出力ファイルを提供します。
  
### <a name="output-format"></a>出力書式

コンプライアンス サービスの出力は、会話 (Conversation 要素) とメッセージ (Messages 要素) によって分類されます。次のコード サンプルに例を示します。
  
```
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
  
```
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Message 要素には、2 つの要素 (Sender、DateTimeUTC) と 3 つの属性 (Type、Content、ID) が含まれます。Sender 要素はメッセージを送信したユーザーを表し、DateTimeUTC 要素はイベントの発生時刻を表します。次のコード サンプルに例を示します。
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

次の表で、メッセージ属性 Type、Content、ID について説明します。
  
**メッセージ要素の属性**

|**属性**|**説明**|**オプションと必要です**|
|:-----|:-----|:-----|
|Type  <br/> |メッセージの型を指定します。メッセージの型については、「Messages 要素のメッセージ型」の表で説明しています。  <br/> |必須  <br/> |
|Content  <br/> |メッセージの内容が含まれます。Type が Join または Part であるメッセージはこの属性を使用しません。  <br/> |省略可能  <br/> |
|ID  <br/> |コンテンツの一意の ID を指定します。この属性は、Type が Chat であるメッセージでのみ使用されます。  <br/> |省略可能  <br/> |
   
各 Sender 要素には、5 つの属性 (Username、ID、Email、Internal、Uri) が含まれます。次の表で、これらの属性について説明します。
  
**送信者要素の属性**

|**属性**|**説明**|**オプションと必要です**|
|:-----|:-----|:-----|
|Username  <br/> |送信者の名前。  <br/> |省略可能  <br/> |
|ID  <br/> |送信者の一意の id。  <br/> |必須  <br/> |
|Email  <br/> |送信者の電子メール アドレスです。  <br/> |省略可能  <br/> |
|Internal  <br/> |ユーザーが内部ユーザーとフェデレーション ユーザーのどちらであるかを指定します。この値が True に設定されている場合、ユーザーは内部ユーザーです。  <br/> |省略可能  <br/> |
|Uri  <br/> |ユーザーの SIP URI では。  <br/> |必須  <br/> |
   
メッセージ要素を含めることができますメッセージの種類を次の例に示します。 また、各要素の使用方法の例を示します。
  
結合のユーザーがチャット ルームに参加します。
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

一部のユーザーは、チャット ルームを離れます。
  
```
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

チャット - 送信者の電子メール アドレスです。
  
```
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat - ユーザーは、チャットの履歴からコンテンツを要求します。
  
```
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

ファイルのアップロード ・ ユーザーは、ファイルをアップロードします。
  
```
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

ファイルのダウンロード - ユーザーは、ファイルをダウンロードします。
  
```
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>既定の永続的なチャット出力 XSD と XSL 変換の例

次のコード サンプルに、コンプライアンス サーバーからの既定の出力が含まれています。
  
```
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
  
```
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


