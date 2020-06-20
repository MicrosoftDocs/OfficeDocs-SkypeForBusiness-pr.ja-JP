---
title: Microsoft Teams の別の組織のユーザーと通信する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 外部アクセス (フェデレーション) とゲスト アクセスを使用して、Microsoft Teams の別の組織のユーザーと通信する方法を説明します。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 8676c45a386a9fb36571e3262a8c70769f45f0a6
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785279"
---
<a name="communicate-with-users-from-other-organizations-in-microsoft-teams"></a>Microsoft Teams の別の組織のユーザーと通信する
======================================================

組織外の人と通信して共同作業する必要がある場合、Microsoft Teams はそれを実現する 2 つの異なる方法を提供します。 1 つ目は、**外部 アクセス** (フェデレーション) であり、別のドメイン (contoso.com など) のユーザーを検索、呼び出し、チャットできます。 2 つ目は、**ゲスト アクセス**であり、メール アドレスを使用して、ゲストとしてチームに個人を追加できます。 組織内の別のユーザーと同じように、ゲストと共同作業できます。

必要に応じて、外部アクセスとゲストアクセスの両方を使用することもできます。

高レベルでの選択方法は次のとおりです (詳細な比較については、「[外部アクセスとゲスト アクセスの比較](#compare-external-and-guest-access)」に移動してください)。

## <a name="external-access"></a>外部アクセス

別のドメインの外部ユーザが会議を検索、呼び出し、チャット、およびセットアップできるソリューションが必要な場合は、**外部アクセス** (フェデレーション) を使用します。 外部ユーザーは、組織のチームまたはチーム リソースにアクセスできません。 Skype for Business (オンラインまたはオンプレミス) または Skype (2020 年初頭に予定) を使用している外部ユーザーと通信する場合は、外部アクセスを選択します。 

Teams では既定で外部アクセスが有効になっています。つまり、組織はすべての外部ドメインと通信できます。 Teams 管理者はこれをオフにするか、含める (または除外する) ドメインを指定できます。 詳細については、「[外部アクセスを管理する](manage-external-access.md)」をご覧ください。 

外部ユーザーがチームとチャネルにアクセスできるようにする場合に適した方法は、[ゲスト アクセス](#guest-access)です。 


## <a name="guest-access"></a>ゲスト アクセス

**ゲスト アクセス**を使用して (ドメインに関係なく) 個々のユーザーをチームに追加し、Word、Excel または PowerPoint などの Microsoft 365 アプリまたは Office 365 アプリを使用して、チャット、通話、会議、組織ファイル (SharePoint または OneDrive for Business に保存されている) での共同作業を行うことができます。 ゲスト ユーザーには、ネイティブ チーム メンバーとほぼ同じ Teams 機能を付与できます。 詳細については、「[Teams でのゲスト アクセス](guest-access.md)」をご覧ください。

- ゲストは組織の Active Directory に追加されます。
- ゲストと通信するには、ゲストはゲスト アカウントを使用して Teams にサインインする必要があります。 つまり、ゲストは Teams アカウントにサインインするために、自分の Teams アカウントからサイン アウトする必要がある場合があります。
- ゲスト ユーザーは、外部アクセス (フェデレーション) ユーザーよりも多くの Teams (ファイル、チーム、チャネルなど) のリソースにアクセスできます。
- Teams 管理者は、ゲストが Teams 管理センターでできること (またはできないこと) をすべて制御します。 詳細については、「[ゲスト アクセスを管理する](manage-guests.md)」をご覧ください。

組織でゲスト アクセスをオンにする準備ができたら、「[ゲスト アクセスのチェックリスト](guest-access-checklist.md)」から始めます。


## <a name="compare-external-and-guest-access"></a>外部アクセスとゲスト アクセスの比較

| 機能 | 外部アクセス ユーザー | ゲスト アクセス ユーザー |
|---------|-----------------------|--------------------|
| ユーザーは別の会社の誰かとチャットできる | はい |はい |
| ユーザーは別の会社の誰かと通話できる | はい | はい |
| ユーザーは別の会社の誰かが通話またはチャットできるかどうかを確認できる | はい | はい<sup>1</sup> |
| ユーザーは外部テナント全体でユーザーを検索できます | はい<sup>2</sup> | いいえ |
| ユーザーはファイルを共有できる | いいえ | Yes |
| ユーザーは Teams のリソースにアクセスできる | いいえ | はい |
| ユーザーをグループ チャットに追加できる | いいえ | Yes |
| ユーザーを会議に招待できる | はい | Yes |
| 追加のユーザーを外部ユーザーとのチャットに追加できる | いいえ<sup>3</sup> | 該当なし |
| ユーザーは外部関係者として識別される | Yes | Yes |
| プレゼンスが表示される | Yes | はい |
| 不在時のメッセージが表示される | いいえ | Yes |
| 個々のユーザーをブロックできる | いいえ | はい |
| @メンションがサポートされている | はい<sup>4</sup> | はい |
| プライベート通話をする | はい | はい |
| ダイヤルイン会議の参加者の電話番号を表示する | No<sup>5</sup> | はい |
| IP ビデオを許可する | Yes | はい |
| 画面共有モード | はい<sup>4</sup> | はい |
| 今すぐ会議を許可する | いいえ | はい |
| 送信済みメッセージを編集する | はい<sup>4</sup> | はい |
| 送信済みメッセージを削除できる | はい<sup>4</sup> | はい |
| 会話で Giphy を使用する | はい<sup>4</sup> | はい |
| 会話でミームを使用する | はい<sup>4</sup> | はい |
| 会話でステッカーを使用する | はい<sup>4</sup> | はい |
||||

<sup>1</sup> ユーザーがゲストとして追加され、ゲスト テナントにゲストとしてサインインしている場合。<br>
<sup>2</sup> 電子メールまたはセッション開始プロトコル (SIP) アドレスのみ。<br>
<sup>3</sup> 外部 (フェデレーション) チャットは 1:1 のみ。<br>
<sup>4</sup> 2 つの異なる組織の Teams のみユーザーの Teams のみの 1:1 チャットでサポートされる。 <br>
<sup>5</sup> 既定では、外部ユーザーはダイヤル インした参加者の電話番号は見ることができません。 これらの電話番号のプライバシーを維持したい場合は、**開始/終了のお知らせの種類** の **トーン** を選びます (これにより、数字が Teams によって読み上げられません)。 詳細については、「[Microsoft Teams で会議の入退室通知をオンまたはオフにする](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)」を参照してください。

## <a name="related-topics"></a>関連項目

[Teams での外部アクセス](manage-external-access.md)

[Teams でのゲスト アクセス](guest-access.md)

