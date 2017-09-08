---
title: "Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: solution
ms.prod: teams
description: "Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加し、チーム メンバーに通知を送信する方法を説明します。"
ms.openlocfilehash: 5e006f8074bd7d5675d84502ccafb0adf29698e3
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Microsoft Teams SMTP ドメインを承認済みドメインとして Exchange Online に追加する 
=============================================================================

管理コンソールに Office 365 グループを作成するか、Outlook を使って Office 365 グループを作成するかに関わらず、グループに追加したチーム メンバーへの通知の送信には Exchange Online が使用されます。通知は、既定のドメイン SMTP FQDN であるテナントから生成されます。

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams は追加済みのチーム メンバーに通知を送信するために Microsoft Exchange Online も使用します。SMTP メッセージのドメイン FQDN の場合は、「@email.teams.microsoft.com」という形式が使用され、この形式はスパム フィルタリングによって検出されます。次の画像が示すように、Outlook はこのメッセージを外部送信者として認識し、画像や特定のコンテンツの遮断といった標準的なセキュリティ機能を適用します。

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

最良の結果と円滑な操作を実現するため、Microsoft Teams SMTP ドメインを Exchange Online スパム構成の「承認済みドメイン」リストに追加することをお勧めします。

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
