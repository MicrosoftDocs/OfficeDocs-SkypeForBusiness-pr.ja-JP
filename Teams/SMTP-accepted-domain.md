---
title: マイクロソフト チーム SMTP ドメインを追加、許可された送信者のドメインと Exchange オンライン
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anprakas
description: マイクロソフト チーム SMTP ドメインを追加、許可された送信者のドメインと Exchange オンラインのチーム メンバーに通知を送信するについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d69e2890589169da126f237562d32a89d378edb
ms.sourcegitcommit: 046cc4a880f3b6b5f912278483cf28fa25619b6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2018
ms.locfileid: "21597576"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>マイクロソフト チーム SMTP ドメインを追加、許可された送信者のドメインと Exchange オンライン 
=============================================================================

管理コンソールに Office 365 グループを作成するか、Outlook を使って Office 365 グループを作成するかに関わらず、グループに追加したチーム メンバーへの通知の送信には Exchange Online が使用されます。通知は、既定のドメイン SMTP FQDN であるテナントから生成されます。

![Outlook 電子メールの、ユーザーがグループに追加されたことを示すメッセージ ヘッダーの例を示すスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

チームを使用して Microsoft Exchange Online にも追加されたことをチーム メンバーに通知します。 ドメインの FQDN は、SMTP メッセージの違いは、"@email.teams.microsoft.com"し、迷惑メール フィルターによってキャッチされる可能性があります。

![Outlook 電子メールの、ユーザーがグループに追加されたことを示すメッセージ ヘッダーの例を示すスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

最良の結果とシームレスな操作では、Exchange オンラインの迷惑メール構成の「許可された送信者のドメイン] 一覧に、マイクロソフト チームの SMTP ドメインを追加することを検討します。

![Exchange Online スパム構成の [許可] リスト セクションのスクリーンショット。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
