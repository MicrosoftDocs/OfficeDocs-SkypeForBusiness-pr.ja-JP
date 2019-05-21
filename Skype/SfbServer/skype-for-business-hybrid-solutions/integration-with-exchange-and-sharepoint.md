---
title: Exchange と SharePoint との統合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: '概要: Skype for Business Server 2015 と Exchange および SharePoint との統合について説明します。'
ms.openlocfilehash: fa4e6d93dd1538dbeafdb05998c4f57482e0f4f5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294314"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Exchange と SharePoint との統合

**概要:** Skype for Business Server 2015 と Exchange および SharePoint との統合について説明します。

Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010、および SharePoint Server (オンプレミスとオンラインの両方) との統合のために、Skype for Business Server 2015 の展開を構成することができます。 次の表に示す機能は、特に指定のない限り、すべてのクライアントでサポートされています。 クライアントのサポートについて詳しくは、「skype for business および skype for business Online クライアントで[のデスクトップクライアントの機能の比較](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)」をご覧ください。 [](https://go.microsoft.com/fwlink/p/?LinkId=281902)

## <a name="integration-with-exchange-server"></a>Exchange Server との統合

次の表は、Microsoft Exchange Server と統合した場合にハイブリッド展開でサポートされる機能を一覧にしたものです。

 **オンプレミスの Skype for Business Server とオンプレミスの Exchange**


|**機能**|**メモ**|
|:-----|:-----|
|Outlook での IM/プレゼンス  <br/> |詳細については、「 [IM とプレゼンス](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)」を参照してください。  <br/> |
|Outlook を使用したオンライン会議の予約と参加  <br/> |詳細については、「 [Skype For Business server 2015 と Exchange server の統合](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)」を参照してください。  <br/> |
|Outlook Web App の IM/プレゼンス  <br/> |詳細については、「 [Skype For Business Server 2015 でハイブリッド環境を構成](../manage/authentication/configure-a-hybrid-environment.md)する」を参照してください。  <br/> |
|Outlook Web App を使ってオンライン会議をスケジュールして参加する  <br/> ||
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> |詳細については、「モバイル機能の[展開](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)」をご覧ください。  <br/> |
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> Lync 2013 または Skype for Business デスクトップクライアントが必要です。  <br/>  詳細については、「[統合連絡先ストアを使用するように Skype For Business Server 2015 を構成する](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)」を参照してください。  <br/> |
|Lync 2013 クライアント、Skype for Business クライアント、Lync Web App での高解像度の連絡先写真。  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> 詳細については、「 [Skype For Business Server 2015 で高解像度の写真の使用を構成する](../deploy/integrate-with-exchange-server/high-resolution-photos.md)」を参照してください。  <br/> Skype for Business アプリ for MAC とモバイルの写真については、「skype for business Server 2015 および exchange [server のパートナーアプリケーションを構成](../deploy/integrate-with-exchange-server/configure-partner-applications.md)する」の説明に従って、skype For business server と exchange server の統合を設定する必要があります。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーがオンプレミスに属する場合にのみサポートされます。 詳細については、「 [Skype For business のハイブリッドソリューション](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)」を参照してください。 <br/> |
|不在着信した会話履歴と通話ログはユーザーの exchange メールボックスに書き込まれる  <br/> ||
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> 詳細については、「[アーカイブ用の展開チェックリスト](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)」を参照してください。  <br/> |
|アーカイブされたコンテンツの検索  <br/> |Exchange 2016 または Exchange 2013 が必要です。  <br/> |
|ボイス メール  <br/> |詳細については、「[オンプレミスの EXCHANGE UM を展開して Lync Server 2013 ボイスメールを提供する](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)」を参照してください。  <br/> |

 **オンプレミスおよび Exchange Online の Skype for Business Server**


|**機能**|**メモ**|
|:-----|:-----|
|Outlook での IM/プレゼンス  <br/> |詳細については、「[オンプレミスの Skype For Business Server 2015 と Outlook Web App の統合を構成する](../deploy/integrate-with-exchange-server/outlook-web-app.md)」を参照してください。 <br/> |
|Outlook を使用したオンライン会議の予約と参加  <br/> ||
|Outlook Web App の IM/プレゼンス  <br/> |詳細については、「[オンプレミスの Skype For Business Server 2015 と Outlook Web App の統合を構成する](../deploy/integrate-with-exchange-server/outlook-web-app.md)」を参照してください。 <br/> |
|Outlook Web App からオンライン会議をスケジュールして参加する  <br/> |詳細については、「[オンプレミスの Skype For Business Server 2015 と Outlook Web App の統合を構成する](../deploy/integrate-with-exchange-server/outlook-web-app.md)」を参照してください。 <br/> |
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> ||
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> ||
|連絡先リスト (統合連絡先ストア経由)。  <br/> |Lync Server 2013 のみ。 Lync 2013 または Skype for Business デスクトップクライアントが必要です。  <br/> 詳細については、「 [Skype For Business Server 2015 を構成してユニファイド連絡先ストアを使用する](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)」を参照してください。 <br/> |
|Lync 2013 クライアント、Skype for Business クライアント、Lync Web App での高解像度の連絡先写真。  <br/> |詳細については、「 [Skype For Business Server 2015 で高解像度の写真の使用を構成する](../deploy/integrate-with-exchange-server/high-resolution-photos.md)」を参照してください。  <br/> Skype for Business アプリ for MAC および Mobile の写真については、「[オンプレミスの skype For Business server と Outlook Web app](../deploy/integrate-with-exchange-server/outlook-web-app.md)との統合を構成する」の説明に従って、skype For business server 2015 と Exchange server の統合を設定する必要があります。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーがオンプレミスに属する場合にのみサポートされます。 詳細については、「 [Skype For business のハイブリッドソリューション](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)」を参照してください。 <br/> |
|不在着信した会話履歴と通話ログはユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> |詳細については、「[アーカイブ用の展開チェックリスト](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)」を参照してください。  <br/> |
|アーカイブされたコンテンツの検索  <br/> |詳細については、「 [SharePoint 電子情報開示センターの Exchange を構成する](https://go.microsoft.com/fwlink/p/?LinkId=285448)」を参照してください。 <br/> |
|ボイス メール  <br/> |詳細については、「 [Lync Server 2013 ユーザーのボイスメールをホストされた EXCHANGE UM で提供](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)する」を参照してください。  <br/> |

 **Skype for Business Online とオンプレミスの Exchange**


|**機能**|**メモ**|
|:-----|:-----|
|Outlook でのプレゼンス  <br/> ||
|Outlook の電子メールからの IM、PSTN 通話、Skype 通話、またはビデオ通話による返信  <br/> ||
|Outlook を使用したオンライン会議の予約と参加  <br/> ||
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> ||
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> ||
|不在着信した会話履歴と通話ログはユーザーの exchange メールボックスに書き込まれる  <br/> ||
|Lync 2013 または Skype for Business クライアントでの、高解像度の連絡先写真。  <br/> |Exchange 2016 または Exchange 2013 が必要です。 ユーザーが Skype for Business Online を使用している場合、この方法は Lync Web App ではサポートされません。  <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーがオンプレミスに属する場合にのみサポートされます。 詳細については、「 [Skype For business のハイブリッドソリューション](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)」を参照してください。 <br/> |
|不在着信した会話履歴と通話ログはユーザーの Exchange メールボックスに書き込まれる  <br/> ||
|サーバー側の会話履歴  <br/> ||

 **Skype for Business Online と Exchange Online**


|**機能**|**メモ**|
|:-----|:-----|
|Outlook での IM/プレゼンス  <br/> ||
|Outlook を使用したオンライン会議の予約と参加  <br/> ||
|Outlook Web App の IM/プレゼンス  <br/> ||
|Outlook Web App からオンライン会議をスケジュールして参加する  <br/> ||
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> ||
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> ||
|不在着信した会話履歴と通話ログはユーザーの exchange メールボックスに書き込まれる  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |Lync Server 2013 または Skype for Business クライアントが必要  <br/> |
|Lync 2013、Skype for Business クライアント、Lync Web App の高解像度の連絡先写真  <br/> ||
|会議の委任  <br/> |両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーがオンプレミスに属する場合にのみサポートされます。 詳細については、「 [Skype For business のハイブリッドソリューション](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)」を参照してください。 <br/> |
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> ||
|アーカイブされたコンテンツの検索  <br/> ||
|ボイスメール  <br/> ||

## <a name="integration-with-sharepoint"></a>SharePoint との統合

次の表は、SharePoint と統合された場合にハイブリッド展開でサポートされる機能を示しています。

||**オンプレミスの SharePoint**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 オンプレミス** <br/> | スキル検索 <br/>  SharePoint でのプレゼンス <br/> | SharePoint でのプレゼンス <br/> |
|**Skype for Business Online** <br/> | SharePoint でのプレゼンス <br/> | SharePoint でのプレゼンス <br/> |


