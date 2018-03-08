---
title: "Microsoft チーム SMTP ドメインを追加、承認済みドメインとして Exchange Online"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft チーム SMTP ドメインを追加承認済みドメインとして Exchange Online チーム メンバーに通知を送信する方法を学習します。"
ms.openlocfilehash: 70795d466059233f09bf1eeb61c9a977a311936e
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Microsoft チーム SMTP ドメインを追加、承認済みドメインとして Exchange Online 
=============================================================================

管理コンソールでまたは Outlook を使って、Office 365 グループを作成するかどうか Exchange Online を使って、チームのメンバーをグループに追加される通知を送信します。SMTP FQDN の既定のドメインを表していると、テナントからこれらのメッセージが生成されます。

![グループにユーザーを示す例 Outlook メール メッセージ ヘッダーのスクリーン ショットが追加されました。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

チームを使って Microsoft Exchange Online にも追加されたときに、チーム メンバーに通知を送信します。ドメインの FQDN SMTP メッセージの違いは、"@email.teams.microsoft.com"で迷惑メール フィルターによって検出される可能性があります。以下の画像からわかるように、Outlook の画像をブロックなどの標準的なセキュリティ機能や特定のコンテンツの対象となる外部の送信者としてこのメッセージと見なされます。

![グループにユーザーを示す例 Outlook メール メッセージ ヘッダーのスクリーン ショットが追加されました。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

最良の結果とシームレスな操作は、Microsoft チーム SMTP ドメイン リストに追加する、"承認済みドメイン] で、Exchange Online の迷惑メールの構成を検討してください。

![許可のスクリーン ショットは、Exchange Online の迷惑メールの設定] セクションを一覧表示します。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
