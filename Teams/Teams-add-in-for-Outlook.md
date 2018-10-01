---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 10/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6acb497937ad7548f8ffc745d12b0ddd813b3e46
ms.sourcegitcommit: 38efc00dfadc98cebd362877a1239d852f804f06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "25353192"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Outlook で Teams の会議アドインを使用する
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Teams の会議アドインは、Microsoft Teams と Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。 Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。 

![Outlook リボン上の Teams アドインのスクリーンショット。](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> Windows 7 のユーザーは、作業をチームの会議アドインの[Windows でのユニバーサルの C ランタイムの更新プログラム](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)をインストールしなければなりません。

Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。

> [!NOTE]
> Outlook 用の Teams の会議アドインは、現時点では Mac ユーザーは利用できません。

## <a name="authentication-requirements"></a>認証要件

Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。 ユーザーがこの方法を使用せずにサインインしても、Teams クライアントを使用することはできますが、Outlook アドインを使用して Teams のオンライン会議をスケジュール設定することはできません。 これを修正するには、次のいずれかを実行します。

- 先進認証が組織に対して構成されていない場合は、先進認証を構成します。
- 先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。

認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。

## <a name="enable-private-meetings"></a>プライベート会議を有効にする

チームと Skype プラグインのビジネス管理センターの配置を取得するを有効にする必要があります秘密の会議のスケジュール設定を使用できます。 **会議**には、管理センターで、 > **ミーティングのポリシー**、し、 **[全般**] セクションで、表示または非表示**プライベートな会議のスケジュールを許可する**にします)。

![チームとビジネス管理センターの Skype の設定のスクリーン ショットです。](media/teams-add-in-for-outlook-image1.png)

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
- アドインを段階的ロールアウトされているが、組織にまだ利用できない可能性があります。

## <a name="troubleshooting"></a>トラブルシューティング

アドインをインストールするのには Outlook のチーム会議出席できない場合は、これらのトラブルシューティング手順を実行してください。

- Outlook デスクトップ クライアントのすべての利用可能な更新プログラムが適用されていることを確認します。 
- チームのデスクトップ クライアントを再起動します。
- サインアウトして、チームのデスクトップ クライアントにもう一度サインインします。
- Outlook デスクトップ クライアントを再起動します。 (Outlook は、管理者モードで実行されていないことを確認してください。)
- ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。 (これは既知の問題、今後のアップデートで修正される予定)
- シングル サインオン (SSO) が有効になっていることを確認します。

アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。

Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

