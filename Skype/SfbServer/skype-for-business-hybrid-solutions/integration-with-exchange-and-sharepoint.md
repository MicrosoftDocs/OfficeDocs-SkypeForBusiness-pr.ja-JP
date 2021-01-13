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
description: '概要: Skype for Business Server 2015 と Exchange および SharePoint の統合について説明します。'
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821107"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Exchange および SharePoint との統合

**概要:** Skype for Business Server 2015 と Exchange および SharePoint の統合について説明します。

Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010、および SharePoint Server (オンプレミスとオンラインの両方) との統合のために Skype for Business Server 2015 展開を構成できます。 次の表に示す機能は、特に指定がない限り、すべてのクライアントでサポートされています。 クライアント サポートの詳細については [、Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) Online クライアントの Skype for Business と Skype for Business Online クライアントの比較表のデスクトップ クライアント機能の比較を [参照してください](https://go.microsoft.com/fwlink/p/?LinkId=281902)。

## <a name="integration-with-exchange-server"></a>Exchange Server との統合

次の表に、ハイブリッド展開と統合するときにサポートされる機能をMicrosoft Exchange Server。

 **オンプレミスの Skype for Business Server とオンプレミスの Exchange**


|**機能**|**注**|
|:-----|:-----|
|Outlook での IM/プレゼンス  <br/> |詳細については [、「IM とプレゼンス」を参照してください](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)。  <br/> |
|Outlook を使用してオンライン会議をスケジュールおよび参加する  <br/> |詳細については [、「Skype for Business Server 2015 と Skype for Business Server 2015](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)の統合」を参照Exchange Server。  <br/> |
|Outlook Web App での IM/プレゼンス  <br/> |詳細については [、「Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md)でのハイブリッド環境の構成」を参照してください。  <br/> |
|会議を通じてオンライン会議をスケジュールOutlook Web App  <br/> ||
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでオンライン会議に参加する  <br/> |詳細については、「モビリティの [展開」を参照してください](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)。  <br/> |
|Outlook 予定表の空き時間情報に基づいて状態を公開する  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> Lync 2013 または Skype for Business デスクトップ クライアントが必要です。  <br/>  詳細については、「統合連絡先 [ストアを使用するために Skype for Business Server 2015 を構成する」を参照してください](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 クライアント、Skype for Business クライアント、Lync Web App の高解像度連絡先写真。  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> 詳細については [、「Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md)で高解像度写真の使用を構成する」を参照してください。  <br/> MAC およびモバイル用の Skype for Business アプリの写真については、「Skype for Business Server と Exchange Server でのパートナー アプリケーションの構成」の説明に従って、Skype for Business Server 2015 と Exchange Server の統合を設定する [Exchange Server必要があります](../deploy/integrate-with-exchange-server/configure-partner-applications.md)。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームに設定されている場合、または両方がオンプレミスにホームである場合にのみサポートされます。 詳細については、「Skype for Business ハイブリッド ソリューション」 [を参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|不明な会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> 詳細については、「アーカイブの [展開チェックリスト」を参照してください](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|アーカイブされたコンテンツを検索する  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> |
|ボイス メール  <br/> |詳細については [、「Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)」を参照してください。  <br/> |

 **オンプレミスの Skype for Business Server と Exchange Online**


|**機能**|**注**|
|:-----|:-----|
|Outlook での IM/プレゼンス  <br/> |詳細については [、「Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Outlook を使用してオンライン会議をスケジュールおよび参加する  <br/> ||
|Outlook Web App での IM/プレゼンス  <br/> |詳細については [、「Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|オンライン会議をスケジュールし、会議に参加Outlook Web App  <br/> |詳細については [、「Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでオンライン会議に参加する  <br/> ||
|Outlook 予定表の空き時間情報に基づいて状態を公開する  <br/> ||
|連絡先リスト (統合連絡先ストア経由)。  <br/> |Lync Server 2013 のみ。 Lync 2013 または Skype for Business デスクトップ クライアントが必要です。  <br/> 詳細については、「統合連絡先ストアを使用するために [Skype for Business Server 2015 を構成する」を参照してください。](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 クライアント、Skype for Business クライアント、Lync Web App の高解像度連絡先写真。  <br/> |詳細については [、「Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md)で高解像度写真の使用を構成する」を参照してください。  <br/> MAC およびモバイル用の Skype for Business アプリの写真については、「オンプレミスの Skype for Business Server と Outlook Web App の間の統合を構成する」の説明に従って、Skype for Business Server 2015 と Exchange Server の統合を設定する必要 [があります](../deploy/integrate-with-exchange-server/outlook-web-app.md)。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームに設定されている場合、または両方がオンプレミスにホームである場合にのみサポートされます。 詳細については、「Skype for Business ハイブリッド ソリューション」 [を参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|見つからない会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> |詳細については、「アーカイブの [展開チェックリスト」を参照してください](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|アーカイブされたコンテンツを検索する  <br/> |詳細については[、「Configure Exchange for SharePoint eDiscovery Center」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=285448)。 <br/> |
|ボイス メール  <br/> |詳細については、「Hosted Exchange UM での [Lync Server 2013 ユーザー ボイス メールの提供」を参照してください](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)。  <br/> |

 **Skype for Business Online とオンプレミスの Exchange**


|**機能**|**注**|
|:-----|:-----|
|Outlook でのプレゼンス  <br/> ||
|Outlook 電子メールからの IM、PSTN 通話、Skype 通話またはビデオ通話による応答  <br/> ||
|Outlook を使用してオンライン会議をスケジュールおよび参加する  <br/> ||
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでオンライン会議に参加する  <br/> ||
|Outlook 予定表の空き時間情報に基づいて状態を公開する  <br/> ||
|不明な会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|Lync 2013 または Skype for Business クライアントの高解像度連絡先写真。  <br/> |Exchange 2016 または Exchange 2013 が必要です。 ユーザーが Skype for Business Online にホームを持つ場合、これは Lync Web App ではサポートされません。  <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームに設定されている場合、または両方がオンプレミスにホームである場合にのみサポートされます。 詳細については、「Skype for Business ハイブリッド ソリューション」 [を参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|見つからない会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|サーバー側の会話履歴  <br/> ||

 **Skype for Business Online および Exchange Online**


|**機能**|**注**|
|:-----|:-----|
|Outlook での IM/プレゼンス  <br/> ||
|Outlook を使用してオンライン会議をスケジュールおよび参加する  <br/> ||
|Outlook Web App での IM/プレゼンス  <br/> ||
|オンライン会議をスケジュールし、会議に参加Outlook Web App  <br/> ||
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでオンライン会議に参加する  <br/> ||
|Outlook 予定表の空き時間情報に基づいて状態を公開する  <br/> ||
|不明な会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |Lync Server 2013 または Skype for Business クライアントが必要  <br/> |
|Lync 2013、Skype for Business クライアント、Lync Web App の高解像度連絡先の写真  <br/> ||
|会議の委任  <br/> |両方のユーザーが同じフォレストにオンラインでホームに設定されている場合、または両方がオンプレミスにホームである場合にのみサポートされます。 詳細については、「Skype for Business ハイブリッド ソリューション」 [を参照してください](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> ||
|アーカイブされたコンテンツを検索する  <br/> ||
|ボイスメール  <br/> ||

## <a name="integration-with-sharepoint"></a>SharePoint との統合

次の表に、SharePoint との統合時にハイブリッド展開でサポートされる機能を示します。

||**SharePoint オンプレミス**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 オンプレミス** <br/> | スキル検索 <br/>  SharePoint でのプレゼンス <br/> | SharePoint でのプレゼンス <br/> |
|**Skype for Business Online** <br/> | SharePoint でのプレゼンス <br/> | SharePoint でのプレゼンス <br/> |


