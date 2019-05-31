---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 05/29/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
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
ms.openlocfilehash: c9a5a17f729c8899c5fb7f7f97a65f9bc36c3080
ms.sourcegitcommit: e487637fc122727b41b37961f208ddc0d20a3fce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591640"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Outlook で Teams の会議アドインを使用する
=======================================

Teams 会議アドインを使用すると、ユーザーは Outlook から Teams 会議をスケジュールできます。 Windows、Mac、web、モバイルの Outlook でアドインを使用できます。

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Windows 版 Outlook の Teams 会議アドイン

Teams の会議アドインは、Microsoft Teams と Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。 Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。

![Outlook リボンの Teams 会議アドインのスクリーンショット](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。
> - Windows 7 ユーザーは、Teams 会議アドインを使用するために windows の[windows でユニバーサル C ランタイムの更新プログラム](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)をインストールする必要があります。

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Outlook for Mac の Teams 会議アドイン

Outlook for Mac の office の [会議] ボタンは、16.24.414.0 を実行している場合、outlook for mac のリボンに表示されます。

ユーザーが [**送信**] をクリックすると、会議の座標 (チームの参加リンクとダイヤルイン番号) が会議の出席依頼に追加されます。  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Outlook Web App の Teams 会議アドイン

ユーザーが新しい Outlook on the Web の以前のバージョンをお持ちの場合、Outlook Web App の [Teams 会議] ボタンが新しいイベントの作成の一部として表示されます。 ユーザーが新しい Outlook on the web の初期バージョンを試す方法については、 [Outlook ブログ](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)を参照してください。

![Outlook Web App の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-web.png)

ユーザーが [**送信**] をクリックすると、会議の座標 (チームの参加リンクとダイヤルイン番号) が会議の出席依頼に追加されます。  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Outlook mobile (iOS と Android) での Teams 会議アドイン

[Teams 会議] ボタンは、Outlook iOS と Android アプリの最新のビルドに表示されます。

![Outlook mobile の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-mobile.png)

ユーザーが [**送信**] をクリックすると、会議の座標 (チームの参加リンクとダイヤルイン番号) が会議の出席依頼に追加されます。  

## <a name="authentication-requirements"></a>認証要件

Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。 ユーザーがこの方法を使用せずにサインインしても、Teams クライアントを使用することはできますが、Outlook アドインを使用して Teams のオンライン会議をスケジュール設定することはできません。 これを修正するには、次のいずれかを実行します。

- 先進認証が組織に対して構成されていない場合は、先進認証を構成します。
- モダン認証が設定されているが、ダイアログボックスでキャンセルされた場合は、多要素認証を使用してもう一度サインインするようにユーザーに指示する必要があります。

認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。

## <a name="enable-private-meetings"></a>プライベート会議を有効にする

アドインを展開できるようにするには、Microsoft Teams 管理センターで**プライベート会議のスケジュール**を有効にする必要があります。 管理センターで**Meetings** > **Meeting Policies**に行き、**一般的な**セクションで、**Allow scheduling private meetings**をオンに切り替えるます。)

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。

> [!NOTE]
> ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Teams のアップグレードポリシーと Outlook 用 Teams 会議アドイン

お客様は[、Skype For business から Teams へのアップグレードを選ぶ](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)ことができます。 テナント管理者は、チームの共存モードを使用して、ユーザーに対してこのような旅を定義できます。 テナント管理者は、ユーザーが Skype for Business (諸島モード) と共にチームを使用できるようにするオプションを備えています。 

孤島モードのユーザーが Outlook で会議をスケジュールする場合、通常は、Skype for Business と Teams のどちらの会議をスケジュールするかを選ぶことができます。 Outlook on the web、Outlook Windows、Outlook Mac では、島々モードでは、ユーザーに Skype for Business アドインと Teams アドインの両方が表示されます。 初期リリースの一部の制限により、Outlook mobile では、Skype for Business**または**Teams 会議の作成のみがサポートされています。 詳細については、次の表を参照してください。

| Teams 管理センターでの共存モード | Outlook mobile の既定の会議プロバイダー |
| --------------------------------------|---------------------------------------------|
| アイランド | Skype for Business |
| Skype for Business のみ | Skype for Business |
| Skype for Business と Teams でのコラボレーション | Skype for Business |
| Skype for Business と Teams でのコラボレーションおよび会議 | Teams |
| Teams のみ | Teams |

## <a name="other-considerations"></a>その他の考慮事項

Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。

- このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。 チャネル会議は Teams 内でスケジュール設定される必要があります。
- 認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。
- ユーザーは Outlook 内からライブイベントをスケジュールできません。 [チームに移動して、ライブイベントのスケジュールを設定します。 詳細については、「 [Microsoft Teams のライブイベントとは](teams-live-events/what-are-teams-live-events.md)」を参照してください。

## <a name="troubleshooting"></a>トラブルシューティング

Teams Meeting add-in for Outlook のアドインをインストールできない場合は、次のトラブルシューティングの手順を試してください。

- Outlook デスクトップクライアントで利用できるすべての更新プログラムが適用されていることを確認します。
- Teamsのデスクトップ クライアントを再起動します。
- [Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。
- Outlook デスクトップ クライアントを再起動します。 (管理者モードで Outlook が実行されていないことを確認してください。)
- ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。 これは既知の問題であり、今後のビルドで修正される予定です。
- シングル サインオン (SSO) が有効になっていることを確認します。

アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。

Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。
