---
title: ゲスト アクセスと外部アクセスを使用して、組織外の人々とコラボレーションする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Priority
description: 外部アクセス (フェデレーション) とゲスト アクセスを使用して、Microsoft Teams で組織外のユーザーと電話およびチャットし、ユーザーを検索および追加する方法を説明します。
ms.openlocfilehash: 10ce0e7f89872a7fda842871d17f8bd06481193f
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461047"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>ゲスト アクセスと外部アクセスを使用して、組織外の人々とコラボレーションする

組織外のユーザーとコミュニケーションや共同作業を行う必要がある場合、Microsoft Teams には次の 2 つのオプションがあります。

- **外部アクセス** - ユーザーが他の組織のユーザーを検索、通話、およびチャットできるようにするフェデレーションの一種です。 これらのユーザーは、ゲストとして招待されない限り、チームに追加できません。
- **ゲスト アクセス** - ゲスト アクセスでは、組織外のユーザーをチームに招待できます。 招待されたユーザーは、Azure Active Directory でゲスト アカウントを取得します。

Teams を使用すると、組織外のユーザーを会議に招待できます。 これには、外部アクセスまたはゲスト アクセスを構成する必要はありません。

## <a name="external-access-federation"></a>外部アクセス (フェデレーション)

Teams、Skype for Business (オンラインまたはオンプレミス)、Skype を使用する組織外のユーザーを検索、電話、チャット、および会議を設定する必要がある場合は、外部アクセスを設定します。 

既定では、すべてのドメインに対して外部アクセスが有効になっています。 外部アクセスを制限するには、特定のドメインを許可またはブロックするか、またはオフにします。

![外部アクセス設定のスクリーンショット](media/external-access-federation-settings.png)

外部アクセスを構成するには、「[外部アクセスの管理](manage-external-access.md)」を参照してください。 

>[!NOTE]
>Microsoft Teams の無料ライセンスでは、外部アクセスはサポートされていません。

## <a name="guest-access"></a>ゲスト アクセス

ゲスト アクセスを使用して、チャット、通話、会議、およびファイル上での共同作業が可能な、組織外のユーザーをチームに追加します。 ゲストには、ネイティブ チーム メンバーとほぼ同じ Teams 機能を使用できるように設定できます。

ゲストは組織の Azure Active Directory に B2B ユーザーとして追加され、ゲスト アカウントを使用して Teams にサインインする必要があります。 つまり、ゲストがお客様の組織にサインインするには、ゲスト自身の組織からサインアウトする必要がある場合があります。

Teams のゲスト アクセスを構成する方法については、「[チームでゲストと共同作業する](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」を参照してください。

## <a name="compare-external-and-guest-access"></a>外部アクセスとゲスト アクセスの比較

次の表に、外部アクセス (フェデレーション) とゲストの使用の違いを示します。 いずれの場合も、組織外のユーザーは外部のユーザーとして識別されます。

### <a name="things-your-users-can-do"></a>ユーザーが実行できる操作

| ユーザーは、次のことを実行できます | 外部アクセス ユーザー | ゲスト |
|---------|-----------------------|--------------------|
| 別の組織のユーザーとチャットする | はい | はい |
| 別の組織のユーザーに電話をかける | はい | はい |
| 別の組織のユーザーが通話またはチャットできるかどうかを確認する | はい | はい<sup>1</sup> |
| 別の組織内のユーザーを検索する | はい<sup>2</sup> | いいえ |
| ファイルを共有する | いいえ | はい |
| 別の組織のユーザーの不在メッセージを見る | いいえ | はい |
| 別の組織のユーザーをブロックする  | いいえ | はい |
| @メンションを使用する | はい<sup>3</sup> | はい |

### <a name="things-people-outside-your-organization-can-do"></a>組織外のユーザーが実行できる操作

| 組織外のユーザーは、次のことを実行できます | 外部アクセス ユーザー | ゲスト |
|---------|-----------------------|--------------------|
| Teams のリソースにアクセスする | いいえ | はい |
| グループ チャットに追加される | いいえ | はい |
| 会議に招待される | はい | はい |
| プライベート通話をする | はい | はい<sup>5</sup> |
| ダイヤルイン会議の参加者の電話番号を表示する | いいえ<sup>4</sup> | はい |
| IP ビデオを使う | はい | はい<sup>5</sup> |
| 画面共有を使う | はい<sup>3</sup> | はい<sup>5</sup> |
| 今すぐ会議を使う | いいえ | はい<sup>5</sup> |
| 送信済みメッセージを編集する | はい<sup>3</sup> | はい<sup>5</sup> |
| 送信済みメッセージを削除する | はい<sup>3</sup> | はい<sup>5</sup> |
| 会話で Giphy を使用する | はい<sup>3</sup> | はい<sup>5</sup> |
| 会話でミームを使用する | はい<sup>3</sup> | はい<sup>5</sup> |
| 会話でステッカーを使用する | はい<sup>3</sup> | はい<sup>5</sup> |
| プレゼンスが表示される | Yes | はい |
| @メンションを使用する | はい<sup>3</sup> | はい |

<br>

<sup>1</sup> ユーザーがゲストとして追加され、ゲスト アカウントでサインインされている場合。<br>
<sup>2</sup> メールまたはセッション開始プロトコル (SIP) アドレスのみ。<br>
<sup>3</sup> 2 つの異なる組織の Teams のみユーザーの Teams のみの 1:1 チャットでサポートされる。 <br>
<sup>4</sup> 既定では、外部ユーザーはダイヤル インした参加者の電話番号は見ることができません。 これらの電話番号のプライバシーを維持したい場合は、**開始/終了のお知らせの種類** の **トーン** を選びます (これにより、数字が Teams によって読み上げられません)。 詳細については、「[Microsoft Teams で会議の入退室通知をオンまたはオフにする](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)」を参照してください。 <br>
<sup>5</sup> 既定で許可されていますが、Teams 管理者がオフにすることができます

## <a name="related-topics"></a>関連項目

[Teams での外部アクセス](manage-external-access.md)

[Teams でのゲスト アクセス](guest-access.md)

