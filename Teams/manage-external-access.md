---
title: Microsoft Teams での外部アクセス (フェデレーション) の管理
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: IT 管理者は、他のドメインの外部アクセス (フェデレーション) を構成して、これらのドメインのユーザーが Teams に参加できるようにすることができます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702721"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>Microsoft Teams での外部アクセス (フェデレーション) の管理
======================================================

Microsoft Teams の外部アクセスを使用すると、他のドメインのユーザーがチャットや通話に参加することができます。 さらに、Skype for Business Online または Skype for Business オンプレミスを使用している外部ユーザーに参加を許可することもできます。 

外部アクセス (フェデレーション) とゲストアクセスの違いは次のとおりです。

- ゲストアクセスは、個々のユーザーにアクセス許可を付与します。 外部アクセスは、ドメイン全体へのアクセス許可を付与します。

- ゲストアクセスはチーム所有者によって付与されると、ゲストは特定のチームのためのリソース (チャネルディスカッションやファイルなど) に[アクセス](guest-experience.md)し、招待されたチーム内の他のユーザーとチャットすることができます。 外部アクセス (フェデレーションチャット) を使用している場合、外部チャット参加者は招待組織のチームまたはチームリソースにアクセスすることはできません。 1対1のフェデレーションチャットにのみ参加できます。 テナント管理者は、外部関係者に適したコラボレーションのレベルに応じて、2つの通信オプションのいずれかを選ぶことができます。 管理者は、組織のニーズに応じて、いずれか一方または両方の方法を選ぶことができますが、すべてのチームでの共同作業にゲストアクセスを有効にすることをお勧めします。 

外部とゲストのアクセス機能の比較については、次の表を参照してください。

| 機能 | 外部アクセスユーザー | ゲストアクセスユーザー |
|---------|-----------------------|--------------------|
| ユーザーは別の会社の他のユーザーとチャットすることができます | はい |可 |
| ユーザーが別の会社のユーザーに電話をかけることができる | はい | 可 |
| 他の会社のユーザーが通話またはチャットできるかどうかを確認できる | はい | Yes<sup>1</sup> |
| ユーザーは外部テナント全体でユーザーを検索できます | Yes<sup>2</sup> | いいえ |
| ユーザーはファイルを共有できます | いいえ | はい |
| ユーザーはチームリソースにアクセスできます | いいえ | はい |
| ユーザをグループチャットに追加できます | いいえ | はい |
| ユーザーを会議に追加できる | はい | 可 |
| 外部ユーザーとのチャットに追加のユーザーを追加できる | なし<sup>3</sup> | N/A |
| ユーザーは外部関係者として識別される | はい | 可 |
| プレゼンスが表示される | はい | 可 |
| 不在時のメッセージが表示される | いいえ | はい |
| 個々のユーザーをブロックすることができます | いいえ | はい |
| @mentions はサポートされています | いいえ | はい |
| プライベート通話を行う | はい | 可 |
| IP ビデオを許可する | はい | 可 |
| 画面共有モード | はい | 可 |
| 今すぐ会議を許可する | いいえ | はい |
| 送信済みメッセージを編集する | はい | 可 |
| 送信したメッセージを削除できます | はい | 可 |
| 会話で Giphy を使う | はい | 可 |
| スレッドで Memes を使う | はい | 可 |
| 会話でステッカーを使用する | はい | 可 |
||||

<sup>1</sup>ユーザーがゲストとして追加され、ゲストテナントにゲストとしてサインインしていることを示します。<br>
<sup>2</sup>メールまたはセッションの開始プロトコル (SIP) アドレスのみ。<br>
<sup>3</sup>外部 (フェデレーション) チャットは1:1 のみです。

> [!NOTE]
> ゲスト機能とゲストエクスペリエンスの詳細については、「 [Microsoft Teams へのゲストアクセスを有効または無効にする](https://docs.microsoft.com/microsoftteams/set-up-guests)」および「[ゲストエクスペリエンスの概要](https://docs.microsoft.com/microsoftteams/guest-experience)」を参照してください。

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a>外部アクセスを有効または無効にする (ユーザーは Skype for Business および Teams ユーザーと通信できます)

Microsoft Teams & Skype for Business 管理センターを使用して、外部アクセスを管理することができます。

1. Microsoft Teams & Skype for business 管理センターで、[**組織全体の設定** > ] の [**外部アクセス**] を選択します。

     ![組織全体の設定の外部アクセスのスクリーンショット](media/manage-external-access-1.png).

2. ユーザーが**Skype For business および Teams ユーザーと通信できるよう**に切り替えるには、 **[オン**] または [**オフ**] に切り替えます。

     ![外部アクセススイッチがオンになっているスクリーンショット](media/manage-external-access-2.png).

3. [**保存**] をクリックします。 

## <a name="add-or-block-a-domain"></a>ドメインを追加またはブロックする

ドメインを追加する、またはドメインの外部アクセスを無効にするには、次の手順を実行します。

1. Microsoft Teams & Skype for business 管理センターで、[**組織全体の設定** > ] の [**外部アクセス**] を選択します。

2. [**ドメインの追加**] を選択します。 
 
    ![[ドメインの追加] リンクが表示された外部アクセスページのスクリーンショット](media/manage-external-access-3.png).

   [**ドメインの追加**] ウィンドウが表示されます。

    ![[ドメインの追加] ウィンドウのスクリーンショット](media/manage-external-access-4.png).


3. [**ドメインの追加**] で、ドメインの名前を入力します。たとえば、「Contoso.com」と入力します。

4. [**許可**] または [**禁止**]を選択します。 この設定はいつでも変更できます。

2. [**完了**] を選びます。

ドメインを追加した後、[外部アクセス] ページのドメインの一覧に、[ドメイン名] と [状態] が表示されます。

## <a name="more-information"></a>詳細情報

Microsoft Teams のゲストアクセスの詳細については、「 [Microsoft teams でゲストアクセスを管理](manage-guests.md)する」を参照してください。
