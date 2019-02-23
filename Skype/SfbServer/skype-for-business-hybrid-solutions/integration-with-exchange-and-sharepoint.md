---
title: Exchange と SharePoint との統合
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
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
description: '概要: は、Exchange と SharePoint サーバー 2015 のビジネス統合のための Skype について説明します。'
ms.openlocfilehash: 98e84fdac1e070c10bdcfb99278e78fb6f56a9a6
ms.sourcegitcommit: e378b8652be6319755a04eb820761364c7faa916
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "30210623"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Exchange と SharePoint との統合

**の概要:** Exchange と SharePoint サーバー 2015 のビジネス統合のため、Skype について説明します。

ビジネス サーバー 2015 2016 の Microsoft Exchange Server、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010、および両方の設置型の SharePoint サーバーとの統合の展開では Skype を構成することができ、オンラインです。 次の表に示す機能は、特に指定のない限り、すべてのクライアントでサポートされています。 クライアントの詳細についてはサポートは、[ビジネス オンラインの Skype のクライアント](https://go.microsoft.com/fwlink/p/?LinkId=281902)でクライアント比較表をオンライン ビジネスの[ビジネス用の Skype のデスクトップ クライアントの機能の比較](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)と Skype を参照してください。

## <a name="integration-with-exchange-server"></a>Exchange Server との統合

次の表は、Microsoft Exchange Server と統合されたときは、ハイブリッド展開でサポートされる機能を一覧表示します。

 **社内のビジネス サーバーと社内の Exchange の Skype**


|**機能**|**メモ**|
|:-----|:-----|
|Outlook での IM/プレゼンス  <br/> |詳細については、 [IM およびプレゼンス](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)を参照してください。  <br/> |
|Outlook を使用したオンライン会議の予約と参加  <br/> |詳細については、 [Exchange Server でサーバー 2015 のビジネス用の Skype の統合](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)を参照してください。  <br/> |
|Outlook Web App では、IM とプレゼンス  <br/> |詳細については、 [Skype のビジネス サーバー 2015 のハイブリッド環境を構成する](../manage/authentication/configure-a-hybrid-environment.md)を参照してください。  <br/> |
|Outlook Web App でオンライン会議をスケジュールし、結合  <br/> ||
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> |詳細については、[モビリティの展開](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)を参照してください。  <br/> |
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |2016 の Exchange または Exchange 2013 が必要です。  <br/> Lync 2013 または Skype のビジネス デスクトップ クライアントが必要です。  <br/>  詳細については、[統合連絡先ストアを使用するサーバー 2015 のビジネス用の Skype の構成](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)を参照してください。  <br/> |
|Lync 2013 クライアント、Skype のビジネスのクライアントと Lync Web App で連絡先の写真を高解像度です。  <br/> |2016 の Exchange または Exchange 2013 が必要です。  <br/> 詳細については、[構成サーバー 2015 のビジネス用の Skype の高解像度の写真の使用](../deploy/integrate-with-exchange-server/high-resolution-photos.md)を参照してください。  <br/> MAC とモバイル用ビジネス アプリケーションの Skype の写真は[Skype ビジネス サーバーと Exchange Server 用に構成するパートナーのアプリケーション](../deploy/integrate-with-exchange-server/configure-partner-applications.md)で説明するようにビジネス サーバー 2015 の Skype と Exchange Server との統合を設定する必要があります。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーがオンプレミスに属する場合にのみサポートされます。 詳細については、[ハイブリッド ソリューションのビジネス用の Skype](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)を参照してください。 <br/> |
|不在着信の会話の履歴とログの呼び出しは、ユーザーの exchange メールボックスに書き込まれます。  <br/> ||
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> |2016 の Exchange または Exchange 2013 が必要です。  <br/> 詳細については、[アーカイブの展開のチェックリスト](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)を参照してください。  <br/> |
|アーカイブされたコンテンツの検索  <br/> |2016 の Exchange または Exchange 2013 が必要です。  <br/> |
|ボイス メール  <br/> |詳細について[を展開する設置型 Exchange UM は、Lync Server 2013 ボイスメールを](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)参照してください。  <br/> |

 **社内のビジネス サーバーと Exchange のオンラインの Skype**


|**機能**|**メモ**|
|:-----|:-----|
|Outlook での IM/プレゼンス  <br/> |詳細については、[設置型の Skype ビジネス サーバー 2015 と Outlook Web App の構成の統合](../deploy/integrate-with-exchange-server/outlook-web-app.md)を参照してください。 <br/> |
|Outlook を使用したオンライン会議の予約と参加  <br/> ||
|Outlook Web App では、IM とプレゼンス  <br/> |詳細については、[設置型の Skype ビジネス サーバー 2015 と Outlook Web App の構成の統合](../deploy/integrate-with-exchange-server/outlook-web-app.md)を参照してください。 <br/> |
|Outlook Web App からオンライン会議をスケジュールし、結合  <br/> |詳細については、[設置型の Skype ビジネス サーバー 2015 と Outlook Web App の構成の統合](../deploy/integrate-with-exchange-server/outlook-web-app.md)を参照してください。 <br/> |
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> ||
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> ||
|連絡先リスト (統合連絡先ストア経由)。  <br/> |Lync Server 2013 のみです。 Lync 2013 または Skype のビジネス デスクトップ クライアントが必要です。  <br/> 詳細については、[統合連絡先ストアを使用するサーバー 2015 のビジネス用の Skype の構成](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)を参照してください。 <br/> |
|Lync 2013 クライアント、Skype のビジネスのクライアントと Lync Web App で連絡先の写真を高解像度です。  <br/> |詳細については、[構成サーバー 2015 のビジネス用の Skype の高解像度の写真の使用](../deploy/integrate-with-exchange-server/high-resolution-photos.md)を参照してください。  <br/> 、MAC、モバイル用ビジネス アプリケーションの Skype の写真は[ビジネス サーバーおよび Outlook Web App の設置型の Skype の間の統合の構成](../deploy/integrate-with-exchange-server/outlook-web-app.md)で説明したようにビジネス サーバー 2015 の Skype と Exchange Server との統合を設定する必要があります。 <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーがオンプレミスに属する場合にのみサポートされます。 詳細については、[ハイブリッド ソリューションのビジネス用の Skype](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)を参照してください。 <br/> |
|不在着信の会話の履歴とログの呼び出しは、ユーザーの Exchange メールボックスに書き込まれます。  <br/> ||
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> |詳細については、[アーカイブの展開のチェックリスト](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)を参照してください。  <br/> |
|アーカイブされたコンテンツの検索  <br/> |詳細については、「[SharePoint の電子情報開示センター用の Exchange の構成](https://go.microsoft.com/fwlink/p/?LinkId=285448)」を参照してください。 <br/> |
|ボイス メール  <br/> |詳細については、[提供する Lync Server 2013 ユーザー ボイス メールでホストされている Exchange UM](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)を参照してください。  <br/> |

 **オンライン ビジネスとの社内の Exchange の Skype**


|**機能**|**メモ**|
|:-----|:-----|
|Outlook でのプレゼンス  <br/> ||
|Outlook の電子メールからの IM、PSTN 通話、Skype 通話、またはビデオ通話による返信  <br/> ||
|Outlook を使用したオンライン会議の予約と参加  <br/> ||
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> ||
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> ||
|不在着信の会話の履歴とログの呼び出しは、ユーザーの exchange メールボックスに書き込まれます。  <br/> ||
|Lync 2013 またはビジネス クライアント用の Skype の連絡先の写真を高解像度です。  <br/> |2016 の Exchange または Exchange 2013 が必要です。 ビジネス オンラインの Skype のユーザーが置かれている場合は、Lync Web App でサポートこのされていません。  <br/> |
|会議の委任  <br/> |両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーがオンプレミスに属する場合にのみサポートされます。 詳細については、[ハイブリッド ソリューションのビジネス用の Skype](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)を参照してください。 <br/> |
|不在着信の会話の履歴とログの呼び出しは、ユーザーの Exchange メールボックスに書き込まれます。  <br/> ||
|サーバー側の会話履歴  <br/> ||

 **ビジネスをオンラインで Skype および Exchange オンライン**


|**機能**|**メモ**|
|:-----|:-----|
|Outlook での IM/プレゼンス  <br/> ||
|Outlook を使用したオンライン会議の予約と参加  <br/> ||
|Outlook Web App では、IM とプレゼンス  <br/> ||
|Outlook Web App からオンライン会議をスケジュールし、結合  <br/> ||
|モバイル クライアントでの IM/プレゼンス  <br/> ||
|モバイル クライアントでのオンライン会議への参加  <br/> ||
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> ||
|不在着信の会話の履歴とログの呼び出しは、ユーザーの exchange メールボックスに書き込まれます。  <br/> ||
|連絡先リスト (統合連絡先ストア経由)  <br/> |Lync Server 2013 または Skype のビジネス クライアントが必要です。  <br/> |
|Lync 2013 は、Skype のビジネス クライアントでは、Lync Web App で連絡先の写真を高解像度  <br/> ||
|会議の委任  <br/> |両方のユーザーが同じフォレスト内で常時オンラインである場合、または両方のユーザーがオンプレミスに属する場合にのみサポートされます。 詳細については、[ハイブリッド ソリューションのビジネス用の Skype](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)を参照してください。 <br/> |
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> ||
|アーカイブされたコンテンツの検索  <br/> ||
|ボイスメール  <br/> ||

## <a name="integration-with-sharepoint"></a>SharePoint との統合

次の表は、SharePoint と統合されたときは、ハイブリッド展開でサポートされる機能を一覧します。

||**SharePoint 設置**|**SharePoint オンライン**|
|:-----|:-----|:-----|
|**Skype ビジネス サーバー 2015 の設置** <br/> | スキル検索 <br/>  SharePoint に存在 <br/> | SharePoint に存在 <br/> |
|**Skype for Business Online** <br/> | SharePoint に存在 <br/> | SharePoint に存在 <br/> |


