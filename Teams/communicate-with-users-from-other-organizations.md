---
title: ゲスト アクセスと外部アクセスを使用して、組織外の人々とコラボレーションする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
description: 外部アクセスとゲスト アクセスを使用して、Microsoft Teams で組織外のユーザーと電話およびチャットし、ユーザーを検索および追加する方法を説明します。
ms.openlocfilehash: f416453a93c07945f9df55c863f76cbb8b736a78
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198319"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>ゲスト アクセスと外部アクセスを使用して、組織外の人々とコラボレーションする

この記事では、組織外の人々と協力するための 2 つのオプションについて説明します。

- **外部アクセス** - ユーザーが他の組織のユーザーを検索、通話、およびチャットできるようにするフェデレーションの一種です。 これらのユーザーは、ゲストとして招待されない限り、チームに追加できません。
- **ゲスト アクセス** - ゲスト アクセスでは、組織外のユーザーをチームに招待できます。 招待されたユーザーは、Azure Active Directory でゲスト アカウントを取得します。

Microsoft 365 の外部コラボレーションの完全な概要については、「[Microsoft 365 の外部コラボレーション オプションの概要](/microsoft-365/enterprise/external-guest-access)」を参照してください。

## <a name="external-access-external-chat-and-meetings"></a>外部アクセス (外部チャットおよび会議)

Teams、Skype for Business (オンラインまたはオンプレミス)、Skype を使用する組織外のユーザーを検索、電話、チャット、および会議を設定する必要がある場合は、外部アクセスを設定します。 

既定では、すべてのドメインに対して外部アクセスが有効になっています。 外部アクセスを制限するには、特定のドメインを許可またはブロックするか、またはオフにします。

![外部アクセス設定のスクリーンショット。](media/external-access-federation-settings.png)

外部アクセスは、次のテナントで使用できます。
- マネージド エンタープライズ アカウント
     - 商用間のみ
     - GCC 間のみ
     - GCC High 間のみ
     - DOD 間のみ
- アンマネージド (個人用) アカウント
     - 商用アカウントと個人アカウントの間のみ
- Skype for Business相互運用機能
     - 商用、GCC、GCC High、DoD の間と全体
- Skype 相互運用機能
     - 商用と Skype の間のみ

外部アクセスを構成するには、「[外部アクセスの管理](manage-external-access.md)」を参照してください。 

>[!NOTE]
> [Microsoft Teams 無料版 (クラシック)](https://support.microsoft.com/office/welcome-to-microsoft-teams-free-classic-6d79a648-6913-4696-9237-ed13de64ae3c) ライセンスでは、外部アクセスはサポートされていません。

## <a name="guest-access"></a>ゲスト アクセス

ゲスト アクセスを使用して、チャット、通話、会議、およびファイル上での共同作業が可能な、組織外のユーザーをチームに追加します。 ゲストには、ネイティブ チーム メンバーとほぼ同じ Teams 機能を使用できるように設定できます。 詳細については、[Teamsのゲスト エクスペリエンス](guest-experience.md)を参照してください。

ゲストは B2B コラボレーション ユーザーとして組織の Azure Active Directory に追加され、ゲスト アカウントを使用して Teams にサインインする必要があります。 つまり、ゲストがお客様の組織にサインインするには、ゲスト自身の組織からサインアウトする必要がある場合があります。

ゲスト アクセスは、次のテナントで使用できます。

- 商用と GCC の間で
- GCC High 間のみ
- DOD 間のみ

Teams のゲスト アクセスを構成する方法については、「[チームでゲストと共同作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。

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
| グループ チャットに追加される | はい | はい |
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
<sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams). To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md). <br>
<sup>5</sup> 既定で許可されていますが、Teams 管理者がオフにすることができます

## <a name="related-topics"></a>関連項目

[Teams での外部アクセス](manage-external-access.md)

[Teams でのゲスト アクセス](guest-access.md)
