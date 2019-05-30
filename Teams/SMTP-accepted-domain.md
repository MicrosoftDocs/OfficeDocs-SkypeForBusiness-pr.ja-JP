---
title: Microsoft Teams SMTP ドメインを承認済みの送信者ドメインとして Exchange Online に追加する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Exchange Online で許可された送信者ドメインとして Microsoft Teams SMTP ドメインを追加して、チームメンバーに通知を送信する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcd4fe932d70cfacb3a4856fae68a5a1a81a94ad
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548862"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Microsoft Teams SMTP ドメインを承認済みの送信者ドメインとして Exchange Online に追加する 
=============================================================================

管理コンソールに Office 365 グループを作成するか、Outlook を使って Office 365 グループを作成するかに関わらず、グループに追加したチーム メンバーへの通知の送信には Exchange Online が使用されます。通知は、既定のドメイン SMTP FQDN であるテナントから生成されます。

![グループに追加されたユーザーを示すメッセージヘッダーのスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

チームは、Microsoft Exchange Online を使用して、チームメンバーが追加されたときに通知をチームメンバーに送信します。 SMTP メッセージのドメイン FQDN という違いは、商業用/ビジネス用 @GCC テナントの場合は @email "teams.microsoft.com"、行政テナントの場合は "email.teams.com"、スパムフィルターでキャッチされることがあります。

![グループに追加されたユーザーを示すメッセージヘッダーのスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

最善の結果を得るために、Exchange Online スパム構成の "許可された送信者ドメイン" リストに Microsoft Teams の SMTP ドメインを追加することを検討してください。

![スパム構成設定の [許可リスト] セクションのスクリーンショット](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
