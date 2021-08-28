---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb1898d5c172c6f0ebc4f56cf9059bbb5986077b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586753"
---
# <a name="use-the-teams-meeting-add-in-in-outlook"></a>Outlook で Teams の会議アドインを使用する

Teams 会議アドインを使用すると、ユーザーは Outlook から Teams 会議をスケジュールできます。 このアドインは、Outlook for Windows、Mac、Web、モバイルで使用できます。

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Windows 用 Outlook の Teams 会議アドイン

Teams の会議アドインは、Microsoft Teams と Office 2013、Office 2016 または Office 2019 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。

![Outlook リボン上の Teams 会議アドインのスクリーンショット](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - Teams アドインにリンクする **ダイレクト URL はありません**。
> - 組織で Teams と Skype for Business の両方を使用している場合、その他にも考慮事項があります。 状況によっては、Teams アドインは Outlook では使用できません。 詳細については、「[Skype for Business から Teams へのアップグレード](upgrade-to-Teams-on-prem-tools.md)」を参照してください。
> - Regsvr32.exe ファイルを実行するユーザーのアクセス許可は、コンピューターに Teams 会議アドインをインストールするための最小要件です。
> - Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。
> - Microsoft ストアから Office Outlook のインストールを使用している場合、Teams 会議アドインはサポートされていません。 このアドインが必要なユーザーは、「[S モードでの Windows 10 の Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)」の記事で説明されているとおり、Office のクイック実行バージョンをインストールすることをお勧めします。

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Outlook for Mac の Teams 会議アドイン

Outlook の製品版 16.24.414.0 以降が実行されていて、Microsoft 365 または Office 365 クライアント サブスクリプションでアクティブになっている場合、Outlook for Mac で [Teams 会議] ボタンは Outlook for Mac のリボンに表示されます。

ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Outlook Web App の Teams 会議アドイン

ユーザーが新しい Outlook on the Web の初期バージョンを使用している場合、Outlook Web App の [Teams 会議] ボタンが新しいイベント作成の一部として表示されます。 ユーザーが Outlook on the Web の初期バージョンを試す方法については、「[Outlook のブログ](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)」を参照してください。

![Outlook Web App の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-web.png)

ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Outlook モバイル (iOS および Android) の Teams 会議アドイン

iOS と Android の Outlook アプリの最新ビルドには、Teams 会議ボタンが表示されます。

![Outlook モバイルの Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-mobile.png)

ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Teams 会議アドインと Outlook 用 FindTime

FindTime は、Outlook 用のアドインです。これは、企業全体での会議時間に関するユーザーの合意形成を支援します。 会議の招待者が希望の時間を提示したら、FindTime はユーザーの代わりに会議出席依頼を送信します。 FindTime で [**オンライン会議**] オプションが選択されている場合、FindTime は Skype for Business または Microsoft Teams の会議をスケジュールします。 (FindTime は、既定のオンライン会議チャネルとして、組織が設定したものを使用します。)

> [!NOTE]  
> [Findtime ダッシュボード](https://findtime.microsoft.com/UserDashboard)で Skype for Business の設定を保存した場合、FindTime は Microsoft Teams の代わりにその設定を使用します。 Microsoft Teams を使用する場合は、ダッシュボードの Skype for Business の設定を削除します。

詳細については、「[FindTime で会議をスケジュールする](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)」を参照してください。

## <a name="authentication-requirements"></a>認証要件

Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。 ユーザーがこの方法を使用せずにサインインした場合、Teams クライアントを使用することはできますが、Outlook アドインを使用して [Teams のオンライン会議](https://www.microsoft.com/microsoft-teams/online-meetings)をスケジュール設定することはできません。 これを修正するには、次のいずれかを実行します。

- 先進認証が組織に対して構成されていない場合は、先進認証を構成します。
- 先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。

認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。

## <a name="enable-private-meetings"></a>プライベート会議を有効にする

アドインを展開するには、Microsoft Teams 管理センターで [**プライベート会議のスケジュールを設定できるようになります**] を有効にする必要があります。 管理センターで **Meetings** > **Meeting Policies** に行き、**一般的な** セクションで、**Allow scheduling private meetings** をオンに切り替えるます。)

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。

> [!NOTE]
> ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Teams のアップグレード ポリシーと Outlook 用 Teams 会議アドイン

お客様は、[Skype for Business から Teams へのアップグレード手順を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)ことができます。 テナント管理者は、Teams の共存モードを使用して、ユーザーにこの手順を定義できます。 テナント管理者には、ユーザーが Skype for Business (アイランド モード) と共に Teams を使用できるようにするオプションがあります。

アイランド モードのユーザは、Outlook で会議をスケジュールする場合、通常は Skype for Business と Teams の会議のどちらをスケジュールするか選択できると想定しています。 Outlook on the web、Outlook Windows、および Outlook Mac では、アイランド モードの場合は、既定で Skype for Business および Teams アドインの両方が表示されます。 Teams 会議ポリシー設定を構成して、アイランド モードのユーザーが Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを制御できます。

初期リリースではいくつかの制限があるため、Outlook モバイルは Skype for Business **または** Teams の会議の作成のみをサポートしています。 詳細は次の表を参照してください。

| Teams 管理センターの共存モード | Outlook モバイルの既定の会議プロバイダー |
| --------------------------------------|---------------------------------------------|
| アイランド | Skype for Business |
| Skype for Business のみ | Skype for Business |
| Skype for Business と Teams の共同作業 | Skype for Business |
| Skype for Business と Teams の共同作業と会議 | Teams |
| Teams のみ | Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>アイランド モードのユーザーが Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを設定する

管理者として、組織の Teams 会議ポリシー設定を構成して、*アイランド モードのユーザー* がどの Outlook 会議アドインを使用するかを制御できます。 Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを指定して、Outlook で会議をスケジュールできます。

このポリシーは、アイランドモードで、Teams の会議ポリシーで **AllowOutlookAddIn** パラメーターが **True** に設定されているユーザーにのみ適用できます。 このポリシーを設定する手順については、「[会議ポリシーの設定 - 全般](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode)」を参照してください。

## <a name="other-considerations"></a>その他の考慮事項

Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。

- Teams 会議アドインには、会議をスケジュールするプライマリ ユーザーの Exchange メールボックスが必要です。 Outlook プロファイルに少なくとも 1 つの Exchange メールボックスが構成されていることを確認し、アドインを使用してTeams の会議をスケジュールします。 Exchange の要件の詳細については、「[Exchange とTeams の連携](./exchange-teams-interact.md)」を参照してください。
- このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。 チャネル会議は Teams 内でスケジュール設定される必要があります。
- 認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。
- ユーザーが Outlook 内でライブ イベントをスケジュールすることはできません。 Teams に移動し、ライブ イベントをスケジュールします。 詳細については、「[Microsoft Teams のライブ イベントについて](teams-live-events/what-are-teams-live-events.md)」を参照してください。

[Microsoft Teams での会議と通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)についてご確認ください。

## <a name="troubleshooting"></a>トラブルシューティング

次の手順を使用して、Teams 会議アドインの問題のトラブルシューティングを行います。

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>Outlook for Windows の Teams 会議アドインが表示されない

Outlook 用の Teams 会議アドインをインストールできない場合、次のトラブルシューティングの手順をお試しください。

[Microsoft Support and Recovery Assistant (Microsoft サポート/回復アシスタント)](https://aka.ms/SaRA-TeamsAddInScenario) をダウンロードして、「[Microsoft サポート/回復アシスタントについて](https://aka.ms/SaRA_Home)」の手順に従って自動修正を実行します。

または、次の手順を手動で実行します。

- Windows 7 ユーザーは、Teams 会議アドインを機能させるために、[Windows ユニバーサル C ランタイム更新プログラム](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)をインストールする必要があります。
- ユーザーが Teams で会議をスケジュールできる Teams アップグレード ポリシーを持っていることを確認します。 詳細については、「[Skype for Business から Teams へのアップグレード](/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)」を参照してください。
- Outlook アドインを許可する Teams 会議ポリシーが設定されていることを確認します。 詳細については、「[会議ポリシーの設定 - 全般](./meeting-policies-in-teams-general.md#allow-the-outlook-add-in)」を参照してください。
- ユーザーが Teams デスクトップ クライアントをインストールしていることを確認します。 Teams の Web クライアントのみを使用している場合には、会議アドインはインストールされません。
- ユーザーが Outlook 2013 以降をインストールしていることを確認します。
- ユーザーが regsvr32.exe の実行権限を持っていることを確認します。
- Outlook デスクトップ クライアントのすべての利用可能な更新プログラムが適用されていることを確認します。
- 次の手順を実行します。
  - Teamsのデスクトップ クライアントを再起動します。
  - [Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。
  - Outlook デスクトップ クライアントを再起動します。 (管理者モードで Outlook が実行されていないことをご確認ください。)

それでもアドインが表示されない場合、Outlook でアドインが無効になっていないかをご確認ください。

- Outlook で、[**ファイル**]、[**オプション**] の順に選択します。
- [**Outlook のオプション**] ダイアログ ボックスの [**アドイン**] タブを選択します。
- [**Microsoft Office 用の Microsoft Teams 会議アドイン**] が [**有効なアプリケーション アドイン**] の一覧に表示されていることを確認します。
- Teams 会議アドインが [**無効なアプリケーション アドイン**] の一覧に表示されている場合は、[**管理**] の [**COM アドイン**] を選択し、[**移動**] を選択します。
- [**Microsoft Office 用の Microsoft Teams 会議アドイン**] の横にあるチェックボックスをオンにします。
- すべてのダイアログボックスで [**OK**] をクリックして、Outlook を再起動します。

アドインを管理する方法に関する全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。

それでもアドインが表示されない場合には、次の手順でレジストリ設定を確認します。

> [!NOTE]
> レジストリを正しく編集しないと、システムが正常に動作しなくなる場合があります。 レジストリを変更する前に、コンピューター上の重要なデータをバックアップする必要があります。
- RegEdit.exe を起動します。
- HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins に移動します。
- TeamsAddin.FastConnect が存在することを確認します。
- TeamsAddin.FastConnect 内に LoadBehavior が存在し、3 に設定されていることを確認します。
  - LoadBehavior の値が 3 以外の場合には、3 に変更して Outlook を再起動します。

### <a name="delegate-scheduling-does-not-work"></a>代理人によるスケジュール設定が機能しない

管理者が、[Exchange Web Server (EWS) へのアクセスを制御する](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)ように Microsoft Exchange を構成している場合、代理人は上司の代わりに Teams 会議をスケジュールできません。 この構成のソリューションは開発中で、今後リリースされる予定です。 回避策として、管理者は次の文字列を EWS の許可リストに追加することができます: "*SchedulingService*"。 


## <a name="related-topics"></a>関連項目

- [Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)

- [Outlook から Teams の会議のスケジュールを設定する](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)
