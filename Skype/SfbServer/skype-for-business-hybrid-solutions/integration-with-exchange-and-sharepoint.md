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
description: '概要: Skype for Business Server 2015 と Exchange および SharePoint との統合について説明します。'
ms.openlocfilehash: 01ebbdd94098fa9f7785f41fedbcbdfe7589f03e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092835"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Exchange および SharePoint との統合

**概要:** Skype for Business Server 2015 と Exchange および SharePoint との統合について説明します。

Skype for Business Server 2015 の展開を、Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010、および SharePoint Server (オンプレミスとオンラインの両方) と統合できるよう構成できます。 次の表に示す機能は、特に指定しない限り、すべてのクライアントでサポートされます。 クライアントサポートの詳細については [、「Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) Online のクライアント」の「Skype for Business および Skype for Business Online クライアント比較テーブルのデスクトップ クライアント機能の比較」 [を参照してください](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。

## <a name="integration-with-exchange-server"></a>ユーザーとのExchange Server

次の表に、ハイブリッド展開でサポートされる機能を、ハイブリッド 展開と統合した場合Microsoft Exchange Server。

 **オンプレミスの Skype for Business Server とオンプレミスの Exchange**


|**機能**|**注**|
|:-----|:-----|
|Outlook での IM/Presence  <br/> |詳細については、「IM and [Presence」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)。  <br/> |
|Outlook を通じてオンライン会議をスケジュールして参加する  <br/> |詳細については [、「Integrate Skype for Business Server 2015 with Exchange Server」 を参照してください](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|IM/Presence in Outlook Web App  <br/> |詳細については [、「Configure a hybrid environment in Skype for Business Server 2015」を参照してください](../manage/authentication/configure-a-hybrid-environment.md)。  <br/> |
|オンライン会議のスケジュール設定と参加は、Outlook Web App  <br/> ||
|モバイル クライアントでの IM/Presence  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> |詳細については [、「Deploying Mobility 」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)。  <br/> |
|Outlook 予定表の空き時間情報に基づいて状態を発行する  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> Lync 2013 または Skype for Business デスクトップ クライアントが必要です。  <br/>  詳細については [、「Configure Skype for Business Server 2015 to use the unified contact store」を参照してください](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 クライアント、Skype for Business クライアント、Lync Web App の高解像度連絡先写真。  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> 詳細については [、「Configure use of high-resolution photos in Skype for Business Server 2015」を参照してください](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> MAC とモバイル用の Skype for Business アプリの写真については、「Skype for Business Server 2015 と Exchange Server の間の統合」の説明に従ってセットアップする [必要があります。「Skype for Business Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)および Exchange Server でパートナー アプリケーションを構成する」を参照してください。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームされている場合、または両方がオンプレミスの場合にのみサポートされます。 詳細については [、「Skype for Business ハイブリッド ソリューション」を参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|Exchange でのコンテンツのアーカイブ (IM と会議)  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> 詳細については、「アーカイブ用 [の展開チェックリスト」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)。  <br/> |
|アーカイブされたコンテンツを検索する  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> |
|ボイス メール  <br/> |詳細については [、「Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)。  <br/> |

 **オンプレミスの Skype for Business Server と Exchange Online**


|**機能**|**注**|
|:-----|:-----|
|Outlook での IM/Presence  <br/> |詳細については [、「Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Outlook を通じてオンライン会議をスケジュールして参加する  <br/> ||
|IM/Presence in Outlook Web App  <br/> |詳細については [、「Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|オンライン会議のスケジュール設定と参加は、Outlook Web App  <br/> |詳細については [、「Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|モバイル クライアントでの IM/Presence  <br/> ||
|モバイル クライアントでオンライン会議に参加する  <br/> ||
|Outlook 予定表の空き時間情報に基づいて状態を発行する  <br/> ||
|連絡先リスト (統合連絡先ストア経由)。  <br/> |Lync Server 2013 のみ。 Lync 2013 または Skype for Business デスクトップ クライアントが必要です。  <br/> 詳細については [、「Configure Skype for Business Server 2015 to use the unified contact store」を参照してください。](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 クライアント、Skype for Business クライアント、Lync Web App の高解像度連絡先写真。  <br/> |詳細については [、「Configure use of high-resolution photos in Skype for Business Server 2015」を参照してください](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> Mac とモバイル用の Skype for Business アプリの写真については、「オンプレミスの Skype for Business Server と Outlook Web App の統合を構成する」の説明に従って、Skype for Business Server 2015 と Exchange Server の統合 [を設定する必要があります](../deploy/integrate-with-exchange-server/outlook-web-app.md)。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームされている場合、または両方がオンプレミスの場合にのみサポートされます。 詳細については [、「Skype for Business ハイブリッド ソリューション」を参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|Exchange でのコンテンツのアーカイブ (IM と会議)  <br/> |詳細については、「アーカイブ用 [の展開チェックリスト」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)。  <br/> |
|アーカイブされたコンテンツを検索する  <br/> |詳細については [、「Configure Exchange for SharePoint 電子情報開示センター」を参照してください。](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|ボイス メール  <br/> |詳細については、「ホストされた Exchange UM での [Lync Server 2013 Users Voice Mail の提供」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)。  <br/> |

 **Skype for Business Online および Exchange オンプレミス**


|**機能**|**注**|
|:-----|:-----|
|Outlook でのプレゼンス  <br/> ||
|Outlook の電子メールから IM、PSTN 通話、Skype 通話、またはビデオ通話を介して応答する  <br/> ||
|Outlook を通じてオンライン会議をスケジュールして参加する  <br/> ||
|モバイル クライアントでの IM/Presence  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> ||
|Outlook 予定表の空き時間情報に基づいて状態を発行する  <br/> ||
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|Lync 2013 または Skype for Business クライアントの高解像度連絡先写真。  <br/> |Exchange 2016 または Exchange 2013 が必要です。 ユーザーが Skype for Business Online に参加している場合、これは Lync Web App ではサポートされません。  <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームされている場合、または両方がオンプレミスの場合にのみサポートされます。 詳細については [、「Skype for Business ハイブリッド ソリューション」を参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|サーバー側の会話の履歴  <br/> ||

 **Skype for Business Online および Exchange Online**


|**機能**|**注**|
|:-----|:-----|
|Outlook での IM/Presence  <br/> ||
|Outlook を通じてオンライン会議をスケジュールして参加する  <br/> ||
|IM/Presence in Outlook Web App  <br/> ||
|オンライン会議のスケジュール設定と参加は、Outlook Web App  <br/> ||
|モバイル クライアントでの IM/Presence  <br/> ||
|モバイル クライアントでオンライン会議に参加する  <br/> ||
|Outlook 予定表の空き時間情報に基づいて状態を発行する  <br/> ||
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |Lync Server 2013 または Skype for Business クライアントが必要  <br/> |
|Lync 2013、Skype for Business クライアント、Lync Web App の高解像度連絡先写真  <br/> ||
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームされている場合、または両方がオンプレミスの場合にのみサポートされます。 詳細については [、「Skype for Business ハイブリッド ソリューション」を参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|Exchange でのコンテンツのアーカイブ (IM と会議)  <br/> ||
|アーカイブされたコンテンツを検索する  <br/> ||
|ボイスメール  <br/> ||

## <a name="integration-with-sharepoint"></a>SharePoint との統合

次の表に、SharePoint と統合した場合にハイブリッド展開でサポートされる機能を示します。

||**SharePoint オンプレミス**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 オンプレミス** <br/> | スキル検索 <br/>  SharePoint でのプレゼンス <br/> | SharePoint でのプレゼンス <br/> |
|**Skype for Business Online** <br/> | SharePoint でのプレゼンス <br/> | SharePoint でのプレゼンス <br/> |