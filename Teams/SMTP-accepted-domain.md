---
title: Exchange Online で許可された送信者ドメインとして Teams の SMTP ドメインを追加する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
f1.keywords:
- NOCSH
description: Exchange Online で許可された送信者ドメインとして Microsoft Teams SMTP ドメインを追加して、チームメンバーに通知を送信する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33605a8250c9cd2bdcec90ade7b3fcea536f8977
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582054"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Microsoft Teams SMTP ドメインを承認済みの送信者ドメインとして Exchange Online に追加する 
=============================================================================

管理コンソールで Microsoft 365 グループを作成するか、Outlook を使用して作成したかにかかわらず、グループに追加されているチームメンバーの通知を Exchange Online で送信できます。 これらのメッセージは、既定のドメイン SMTP FQDN を表すため、テナントから生成されます。

![グループに追加されたユーザーを示すメッセージヘッダーのスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

チームは、Microsoft Exchange Online を使用して、チームメンバーが追加されたときに通知をチームメンバーに送信します。 SMTP メッセージのドメイン FQDN という違いは、商業用/ビジネス用 @GCC テナントの場合は @email "teams.microsoft.com"、行政テナントの場合は "email.teams.microsoft.com"、スパムフィルターでキャッチされることがあります。

![グループに追加されたユーザーを示すメッセージヘッダーのスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

最善の結果を得るために、Exchange Online スパム構成の "許可された送信者ドメイン" リストに Microsoft Teams の SMTP ドメインを追加することを検討してください。

![スパム構成設定の [許可リスト] セクションのスクリーンショット](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
