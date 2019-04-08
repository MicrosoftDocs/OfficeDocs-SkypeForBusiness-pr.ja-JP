---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbe0b72c03d8e85deff538924c17dac8f0d3773c
ms.sourcegitcommit: daf65bf09ca57554da744602d2551db53caedde5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "30512990"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Outlook で Teams の会議アドインを使用する
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Teams の会議アドインは、Microsoft Teams と Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。 Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。 

![Outlook リボン上の Teams アドインのスクリーンショット。](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> Windows 7ユーザーは、Teams Meetingアドインを機能させるために、[Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)をインストールする必要があります。

Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。

> [!NOTE]
> Outlook 用の Teams の会議アドインは、現時点では Mac ユーザーは利用できません。

## <a name="authentication-requirements"></a>認証要件

Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。 ユーザーがこの方法を使用せずにサインインしても、Teams クライアントを使用することはできますが、Outlook アドインを使用して Teams のオンライン会議をスケジュール設定することはできません。 これを修正するには、次のいずれかを実行します。

- 先進認証が組織に対して構成されていない場合は、先進認証を構成します。
- 先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。

認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。

## <a name="enable-private-meetings"></a>プライベート会議を有効にする

プラグインを展開するには、Microsoft Teams管理センターで [Allow scheduling for private meetings (プライベート会議の予約を許可する)]を有効にする必要があります。 管理センターで**Meetings** > **Meeting Policies**に行き、**一般的な**セクションで、**Allow scheduling private meetings**をオンに切り替えるます。)

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。

> [!NOTE]
> ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。

## <a name="other-considerations"></a>その他の考慮事項

Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。
- 記録、投票、ホワイトボードの使用などの、一部のオンライン会議の機能はまだ利用できません。
- 会議のオプションは現時点では使用できません。
- 現在のところ、会議に招待できるのは自分の会社内のユーザーのみで、外部ユーザーは会議に参加することができません。
- このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。 チャネル会議は Teams 内でスケジュール設定される必要があります。 現在、Outlook の Teams の会議アドインを利用できるのは Windows ユーザーのみですが、Mac 向けのサポートも近日中に予定されています。
- 認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。
- アドインを段階的にロールアウト中で、あなたの組織ではまだ利用できない場合があります。

## <a name="troubleshooting"></a>トラブルシューティング

Teams Meeting add-in for Outlook のアドインをインストールできない場合は、次のトラブルシューティングの手順を試してください。

- Outlook デスクトップ クライアントのすべての利用可能な更新プログラムが適用されていることを確認します。 
- Teamsのデスクトップ クライアントを再起動します。
- [Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。
- Outlook デスクトップ クライアントを再起動します。 (管理者モードで Outlook が実行されていないことを確認してください。)
- ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。 これは既知の問題であり、今後のビルドで修正される予定です。
- シングル サインオン (SSO) が有効になっていることを確認します。

アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。

Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

