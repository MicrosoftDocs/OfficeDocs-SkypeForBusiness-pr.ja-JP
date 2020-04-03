---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0320a08a5358716472d382482cb9c825d0709e59
ms.sourcegitcommit: 1bb3df681177db5ecc6afae3d3f3a46c251e5c23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "43117435"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Outlook で Teams の会議アドインを使用する
=======================================

Teams 会議アドインを使用すると、ユーザーは Outlook から Teams 会議をスケジュールできます。 このアドインは、Outlook for Windows、Mac、Web、モバイルで使用できます。

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Windows 用 Outlook の Teams 会議アドイン

Teams の会議アドインは、Microsoft Teams と Office 2010、Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。 Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。

![Outlook リボン上の Teams 会議アドインのスクリーンショット](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - 組織で Teams と Skype for Business の両方を実行している場合は、その他の考慮事項があります。 状況によっては、Outlook で Teams アドインを使用できない場合があります。 詳細については、「 [Skype For business から Teams にアップグレードする](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)」を参照してください。
> - Regsvr32.exe ファイルを実行するユーザーのアクセス許可は、コンピューターに Teams 会議アドインをインストールするための最小要件です。
> - Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。
> - Microsoft ストアから Office Outlook のインストールを使用している場合、Teams 会議アドインはサポートされていません。 このアドインが必要なユーザーは、「[S モードでの Windows 10 の Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)」の記事で説明されているとおり、Office のクイック実行バージョンをインストールすることをお勧めします。

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Outlook for Mac の Teams 会議アドイン

Outlook の製品版 16.24.414.0 以降が実行されていて、Office 365 クライアント サブスクリプションでアクティブになっている場合、Outlook for Mac で [Teams 会議] ボタンは Outlook for Mac のリボンに表示されます。

ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Outlook Web App の Teams 会議アドイン

ユーザーが新しい Outlook on the Web の初期バージョンを使用している場合、Outlook Web App の [Teams 会議] ボタンが新しいイベント作成の一部として表示されます。 ユーザーが Outlook on the Web の初期バージョンを試す方法については、「[Outlook のブログ](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)」を参照してください。

![Outlook Web App の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-web.png)

ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Outlook モバイル (iOS および Android) の Teams 会議アドイン

iOS と Android の Outlook アプリの最新ビルドには、Teams 会議ボタンが表示されます。

![Outlook モバイルの Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-mobile.png)

ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a>Outlook の Teams 会議アドインと FindTime
FindTime は、Outlook 用のアドインです。これは、企業全体の会議時間に関してユーザが合意できるようにします。 会議の招待者が希望の時間を提示したら、FindTime はユーザーの代わりに会議出席依頼を送信します。 FindTime で [**オンライン会議**] オプションが選択されている場合、FindTime は Skype for Business または Microsoft Teams の会議をスケジュールします。 (FindTime は、既定のオンライン会議チャネルとして、組織が設定したものを使用します。)

> [!NOTE]  
> [Findtime ダッシュボード](https://findtime.microsoft.com/UserDashboard)で Skype for Business の設定を保存した場合、FindTime は Microsoft Teams の代わりにその設定を使用します。 Microsoft Teams を使用する場合は、ダッシュボードの Skype for Business の設定を削除します。

詳細については、「[FindTime で会議をスケジュールする](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)」を参照してください。

## <a name="authentication-requirements"></a>認証要件

Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。 ユーザーがこのメソッドを使用してサインインしていない場合は、引き続き Teams クライアントを使用できますが、Outlook アドインを使用してチームのオンライン会議をスケジュールすることはできません。 これを修正するには、次のいずれかを実行します。

- 先進認証が組織に対して構成されていない場合は、先進認証を構成します。
- 先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。

認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。

## <a name="enable-private-meetings"></a>プライベート会議を有効にする

アドインを展開するには、Microsoft Teams 管理センターで [**プライベート会議のスケジュールを設定できるようになります**] を有効にする必要があります。 管理センターで**Meetings** > **Meeting Policies**に行き、**一般的な**セクションで、**Allow scheduling private meetings**をオンに切り替えるます。)

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。

> [!NOTE]
> ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Teams のアップグレード ポリシーと Outlook 用 Teams 会議アドイン

お客様は、[Skype for Business から Teams へのアップグレード手順を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)ことができます。 テナント管理者は、Teams の共存モードを使用して、ユーザーにこの手順を定義できます。 テナント管理者には、ユーザーが Skype for Business (アイランド モード) と共に Teams を使用できるようにするオプションがあります。 

アイランド モードのユーザは、Outlook で会議をスケジュールする場合、通常は Skype for Business と Teams の会議のどちらをスケジュールするか選択できると想定しています。 Outlook on the web、Outlook Windows、および Outlook Mac では、アイランド モードの場合、Skype for Business および Teams アドインの両方が表示されます。 初期リリースではいくつかの制限があるため、Outlook モバイルは Skype for Business **または** Teams の会議の作成のみをサポートしています。 詳細は次の表を参照してください。

| Teams 管理センターの共存モード | Outlook モバイルの既定の会議プロバイダー |
| --------------------------------------|---------------------------------------------|
| アイランド | Skype for Business |
| Skype for Business のみ | Skype for Business |
| Skype for Business と Teams の共同作業 | Skype for Business |
| Skype for Business と Teams の共同作業と会議 | Teams |
| Teams のみ | Teams |

## <a name="other-considerations"></a>その他の考慮事項

Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。

- このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。 チャネル会議は Teams 内でスケジュール設定される必要があります。
- 認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。
- ユーザーが Outlook 内でライブ イベントをスケジュールすることはできません。 Teams に移動し、ライブ イベントをスケジュールします。 詳細については、「[Microsoft Teams のライブ イベントについて](teams-live-events/what-are-teams-live-events.md)」を参照してください。

## <a name="troubleshooting"></a>トラブルシューティング

Teams Meeting add-in for Outlook のアドインをインストールできない場合は、次のトラブルシューティングの手順を試してください。

- Outlook デスクトップ クライアントのすべての利用可能な更新プログラムが適用されていることを確認します。
- Teamsのデスクトップ クライアントを再起動します。
- [Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。
- Outlook デスクトップ クライアントを再起動します。 (Outlook が管理者モードで実行されていないことを確認します)。
- ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。 これは既知の問題であり、今後のビルドで修正される予定です。
- シングル サインオン (SSO) が有効になっていることを確認します。

管理者が、[Exchange Web Server (EWS) へのアクセスを制御する](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)ように Microsoft Exchange を構成している場合、代理人は上司の代わりに Teams 会議をスケジュールできません。 この構成のソリューションは開発中で、今後リリースされる予定です。 

アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。

Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。
