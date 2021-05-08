---
title: Exchange および SharePoint との統合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: '概要: 2015 年 2015 Skype for Business Serverとデータの統合ExchangeについてSharePoint。'
ms.openlocfilehash: f8d57924d3a82effbc552de660b973aa36e7b8fe
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52236993"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Exchange および SharePoint との統合

**概要:** 2015 Skype for Business Serverと 2015 年の統合についてExchangeおよびSharePoint。

Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010、SharePoint Server との統合のために、Skype for Business Server 2015 の展開をオンプレミスとオンラインの両方で構成できます。 次の表に示す機能は、特に指定しない限り、すべてのクライアントでサポートされます。 クライアントサポートの詳細については、「Client for Skype for Business Online」の[「Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)および Skype for Business Online クライアント比較テーブルのデスクトップ クライアント機能の比較[」Skype for Business を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>アプリケーションとのExchange Server

次の表に、ハイブリッド展開でサポートされる機能を、ハイブリッド 展開と統合した場合Microsoft Exchange Server。

 **Skype for Business ServerオンプレミスとオンプレミスExchangeの設定**


|**機能**|**注**|
|:-----|:-----|
|IM/Presence in Outlook  <br/> |詳細については、「IM and [Presence」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)。  <br/> |
|オンライン会議をスケジュールし、会議に参加Outlook  <br/> |詳細については[、「Integrate Skype for Business Server 2015 with Exchange Server 」 を参照してください](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|IM/Presence in Outlook Web App  <br/> |詳細については[、「Configure a hybrid environment in Skype for Business Server 2015」を参照](../manage/authentication/configure-a-hybrid-environment.md)してください。  <br/> |
|オンライン会議をスケジュールし、会議に参加Outlook Web App  <br/> ||
|モバイル クライアントでの IM/Presence  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> |詳細については [、「Deploying Mobility 」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)。  <br/> |
|予定表の空き時間情報Outlookに基づいて状態を公開する  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |2016 Exchange 2013 年Exchange必要です。  <br/> Lync 2013 または Skype for Businessデスクトップ クライアントが必要です。  <br/>  詳細については[、「Configure Skype for Business Server 2015 で統合連絡先ストアを使用する」を参照してください](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 クライアント、クライアント、および Lync Web App Skype for Business高解像度連絡先写真。  <br/> |2016 Exchange 2013 年Exchange必要です。  <br/> 詳細については、「Configure use of high-resolution photos in the Skype for Business Server [2015」を参照](../deploy/integrate-with-exchange-server/high-resolution-photos.md)してください。  <br/> mac および Mobile 用 Skype for Business アプリの写真については、「Skype for Business Server と Exchange Server でパートナー アプリケーションを構成する」の説明に従って、Skype for Business Server 2015 と Exchange Server の統合を設定する[必要があります](../deploy/integrate-with-exchange-server/configure-partner-applications.md)。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームされている場合、または両方がオンプレミスの場合にのみサポートされます。 詳細については、「ハイブリッド ソリューションSkype for Business[参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|アーカイブ コンテンツ (IM と会議) Exchange  <br/> |2016 Exchange 2013 年Exchange必要です。  <br/> 詳細については、「アーカイブ用 [の展開チェックリスト」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)。  <br/> |
|アーカイブされたコンテンツを検索する  <br/> |2016 Exchange 2013 年Exchange必要です。  <br/> |
|ボイス メール  <br/> |詳細については[、「Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail 」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)。  <br/> |

 **Skype for Business ServerおよびオンプレミスのExchange Online**


|**機能**|**注**|
|:-----|:-----|
|IM/Presence in Outlook  <br/> |詳細については[、「Configure integration between on-premises Skype for Business Server 2015」を参照Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|オンライン会議をスケジュールし、会議に参加Outlook  <br/> ||
|IM/Presence in Outlook Web App  <br/> |詳細については[、「Configure integration between on-premises Skype for Business Server 2015」を参照Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|オンライン会議のスケジュール設定と参加は、Outlook Web App  <br/> |詳細については[、「Configure integration between on-premises Skype for Business Server 2015」を参照Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|モバイル クライアントでの IM/Presence  <br/> ||
|モバイル クライアントでオンライン会議に参加する  <br/> ||
|予定表の空き時間情報Outlookに基づいて状態を公開する  <br/> ||
|連絡先リスト (統合連絡先ストア経由)。  <br/> |Lync Server 2013 のみ。 Lync 2013 または Skype for Businessデスクトップ クライアントが必要です。  <br/> 詳細については[、「Configure Skype for Business Server 2015 to use the unified contact store」を参照してください。](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 クライアント、クライアント、および Lync Web App Skype for Business高解像度連絡先写真。  <br/> |詳細については、「Configure use of high-resolution photos in the Skype for Business Server [2015」を参照](../deploy/integrate-with-exchange-server/high-resolution-photos.md)してください。  <br/> mac および Mobile 用 Skype for Business アプリの写真の場合は、「オンプレミスの Skype for Business Server と Outlook Web App の間の統合を構成する」の説明に従って、Skype for Business Server 2015 と Exchange Server の統合[を設定する必要があります](../deploy/integrate-with-exchange-server/outlook-web-app.md)。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームされている場合、または両方がオンプレミスの場合にのみサポートされます。 詳細については、「ハイブリッド ソリューションSkype for Business[参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|[会話の履歴] と [通話ログ] がユーザーのメールボックスにExchangeされます  <br/> ||
|アーカイブ コンテンツ (IM と会議) Exchange  <br/> |詳細については、「アーカイブ用 [の展開チェックリスト」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)。  <br/> |
|アーカイブされたコンテンツを検索する  <br/> |詳細については、「Configure [Exchange SharePoint」を参照してください。](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|ボイス メール  <br/> |詳細については、「ホストされている UM での[Lync Server 2013 Users](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)Voice Mail の提供」をExchangeしてください。  <br/> |

 **Skype for BusinessオンラインとExchangeオンプレミス**


|**機能**|**注**|
|:-----|:-----|
|プレゼンス イン Outlook  <br/> ||
|IM、PSTN 通話、電話Skypeビデオ通話を経由して、電子メールからOutlookする  <br/> ||
|オンライン会議のスケジュール設定と参加は、Outlook  <br/> ||
|モバイル クライアントでの IM/Presence  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> ||
|予定表の空き時間情報Outlookに基づいて状態を公開する  <br/> ||
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|Lync 2013 またはクライアントの高解像度連絡先Skype for Businessします。  <br/> |2016 Exchange 2013 年Exchange必要です。 Lync Web App では、ユーザーがオンライン上にSkype for Businessされません。  <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームされている場合、または両方がオンプレミスの場合にのみサポートされます。 詳細については、「ハイブリッド ソリューションSkype for Business[参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|[会話の履歴] と [通話ログ] がユーザーのメールボックスにExchangeされます  <br/> ||
|サーバー側の会話の履歴  <br/> ||

 **Skype for BusinessオンラインとExchange Online**


|**機能**|**注**|
|:-----|:-----|
|IM/Presence in Outlook  <br/> ||
|オンライン会議のスケジュール設定と参加は、Outlook  <br/> ||
|IM/Presence in Outlook Web App  <br/> ||
|オンライン会議のスケジュール設定と参加は、Outlook Web App  <br/> ||
|モバイル クライアントでの IM/Presence  <br/> ||
|モバイル クライアントでオンライン会議に参加する  <br/> ||
|予定表の空き時間情報Outlookに基づいて状態を公開する  <br/> ||
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |Lync Server 2013 またはクライアントSkype for Business必要  <br/> |
|Lync 2013、Skype for Business、Lync Web App の高解像度連絡先写真  <br/> ||
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームされている場合、または両方がオンプレミスの場合にのみサポートされます。 詳細については、「ハイブリッド ソリューションSkype for Business[参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|アーカイブ コンテンツ (IM と会議) Exchange  <br/> ||
|アーカイブされたコンテンツを検索する  <br/> ||
|ボイスメール  <br/> ||

## <a name="integration-with-sharepoint"></a>SharePoint との統合

次の表に、ハイブリッド展開でサポートされる機能を、ハイブリッド 展開と統合するときにSharePoint。

||**SharePoint オンプレミス**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 オンプレミス** <br/> | スキル検索 <br/>  プレゼンス イン SharePoint <br/> | プレゼンス イン SharePoint <br/> |
|**Skype for Business Online** <br/> | プレゼンス イン SharePoint <br/> | プレゼンス イン SharePoint <br/> |