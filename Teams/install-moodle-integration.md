---
title: Microsoft Teams と統合された Moodle をインストールする
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Microsoft Teams 用の Moodle オープンソース学習管理システム (LMS) アプリをインストールして構成する方法について説明します。
keywords: Teams の Moodle アプリ統合プラグイン
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 36b966748fe88b8fec803adc7f9f898e247cdec9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508334"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Microsoft Teams と統合された Moodle のインストール

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

世界で最も人気のあるオープンソース学習管理システム (LMS) である [Moodle](https://moodle.org/) が、Microsoft Teams と統合されました。 この統合により、教育者と教師は Moodle コースで共同作業を行い、成績や課題について質問したり、Teams 内で常に最新の通知を受け取ることができます。

IT 管​​理者がこの統合を簡単に設定できるように、オープンソースの Moodle プラグインを次の機能で更新しました。

* Azure AD を使用した Moodle サーバーの自動登録。
* Moodle アシスタント ボットの Azure へのワンクリック展開。
* すべてまたは一部の Moodle コースのチームの自動プロビジョニングおよびチーム登録の自動同期。
* 同期された各チームへの Moodle タブと Moodle アシスタント ボットの自動インストール。 (近日公開予定)
* Moodle アプリをプライベート Teams App Store にワンクリックで公開します。 (近日公開予定)

この統合が提供する機能の詳細については、[こちら](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle)にアクセスしてください。

## <a name="prerequisites"></a>前提条件

このアプリケーションをインストールして構成するには、次のものが必要です。

1. Moodle 管理者の資格情報
2. Azure AD 管理者の資格情報
3. 新しいリソースを作成できる Azure サブスクリプション

## <a name="step-1-install-the-moodle-plugin"></a>手順 1: Moodle プラグインをインストールする

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft Teams での Moodle 統合は、オープンソースの [Moodle プラグイン セット](https://github.com/Microsoft/o365-moodle)を利用しています。 プラグインを Moodle サーバーにインストールするには、以下の手順に従います。

1. まず、[Moodle プラグイン セット](https://moodle.org/plugins/pluginversions.php?plugin=local_o365)をダウンロードして、ローカル コンピューターに保存します。 バージョン 3.5 以降を使用する必要があります。
    * local_o365 プラグインをインストールすると、[auth_oidc](https://moodle.org/plugins/auth_oidc) および [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) プラグインもインストールされます。
1. 管理者として Moodle サーバーにログインし、左側のナビゲーション パネルから **[サイトの管理]** を選択します。
1. **プラグイン** タブを選択し、**[プラグインのインストール]** をクリックします。
1. 「**ZIP ファイルからプラグインをインストールする**」セクションで、**[ファイルを選択する]** ボタンをクリックします。
1. 左側のナビゲーションから **[ファイルをアップロードする]** オプションを選択し、上でダウンロードしたファイルを参照して、**[このファイルをアップロードする**] をクリックします。
1. 左側のナビゲーション パネルから [**サイトの管理**] オプションをもう一度選択して、管理ダッシュボードに戻ります。 **[ローカル プラグイン]** まで下にスクロールし、**[Microsoft Office 365 の統合]** リンクをクリックします。 この構成ページは、このプロセスの残りの部分で使用するため、別のブラウザー タブで開いたままにしておきます。

Moodle プラグインのインストール方法の詳細については、「[Moodle ドキュメント](https://docs.moodle.org/34/en/Installing_plugins)」をご覧ください。

**重要なお知らせ:** このプロセス全体を通してこのページのセットに戻るため、Microsoft 365 または Office 365 の Moodle プラグインの構成ページを別のブラウザー タブで開いたままにします。

*Moodle サイトをまだお持ちではありませんか?* Azure [リポジトリ](https://github.com/azure/moodle)で Moodle をチェックして Moodle インスタンスをすぐに Azure に展開して、必要に応じてカスタマイズすることができます。

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>手順 2: Microsoft 365 または Office 365 プラグインと Azure Active Directory 間の接続を構成する

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

次に、Moodle をアプリケーションとして Azure Active Directory に登録する必要があります。 このプロセスを完了するのに役立つ PowerShell スクリプトを提供しています。 PowerShell スクリプトは、Microsoft 365 または Office 365 組織用の新しい Azure AD アプリケーションをプロビジョニングします。これは、Moodle プラグインによって使用されます。 スクリプトは、Microsoft 365 または Office 365 テナント用にアプリをプロビジョニングし、プロビジョニングされたアプリに必要なすべての返信 URL とアクセス許可を設定し、AppID とキーを返します。 Moodle プラグイン セットアップ ページで生成された AppID とキーを使用して、Azure AD で Moodle サーバーを構成できます。 PowerShell スクリプトが自動化する詳細な手動手順を確認したい場合は、完全な[プラグインのドキュメント](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)でそれらを見つけることができます。

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Microsoft Teams の情報フローの Moodle タブ

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Microsoft Teams の情報フローの Moodle タブの図" />

1. Microsoft 365 または Office 365 統合プラグイン ページから、[**セットアップ**] タブを選択します。
1. **[PowerShell スクリプトのダウンロード]** ボタンをクリックして、ローカル コンピューターに保存します。
1. ZIP ファイルから PowerShell スクリプトを準備する必要があります。 これを行うには、以下のようにします。
    * `Moodle-AzureAD-Powershell.zip` ファイルをダウンロードして展開します。
    * 展開したフォルダーを開きます。
    * `Moodle-AzureAD-Script.ps1` ファイルを右クリックし、**[プロパティ]** を選択します。
    * [プロパティ] ウィンドウの **[全般]** タブで、下部の**セキュリティ**属性の横にある `Unblock` ボックスをオンにします。
    * **[OK]** をクリックします。
    * 展開したフォルダーのディレクトリ パスをコピーします。
1. 次に、PowerShell を管理者として実行します。
    * [開始] をクリックします。
    * PowerShell と入力します。
    * [Windows PowerShell] を右クリックします。
    * [管理者として実行] をクリックします。
1. `cd ...\...\Moodle-AzureAD-Powershell` と入力して、解凍したディレクトリに移動します。ここで `...\...` はディレクトリへのパスです。
1. 次の方法で PowerShell スクリプトを実行します。
    * `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` を入力します。
    * `.\Moodle-AzureAD-Script.ps1` を入力します。
    * ポップアップ ウィンドウで Microsoft 365 または Office 365 管理者アカウントにログインします。
    * Azure AD アプリケーションの名前を入力します (例: Moodle/Moodle プラグイン)。
    * Moodle サーバーの URL を入力します。
    * スクリプトによって生成された**アプリケーションの ID** と**アプリケーションのキー**をコピーして保存します。
1. 次に、ID とキーを Moodle プラグインに追加する必要があります。 プラグイン管理ページに戻ります ([サイトの管理]、[プラグイン]、[Microsoft 365 の統合] の順に移動)。
1. **[セットアップ]** タブで、前にコピーした**アプリケーションの ID** と**アプリケーションのキー**を追加し、[**変更の保存**] をクリックします。
1. ページが更新されると、新しいセクション「**接続方法を選択する**」が表示されます。 **[既定]** というラベルの付いたチェックボックスをクリックしてから、**[変更の保存]** をもう一度クリックします。
1. ページが更新されると、別の新しいセクション「**管理者の同意と追加情報**」が表示されます。
    * **[管理者の同意を提供する]** リンクをクリックし、Microsoft 365 または Office 365 のグローバル管理者の資格情報を入力してから **[同意]** をクリックしてアクセス許可を付与します。
    * **[Azure AD テナント]** フィールドの横にある **[検出]** ボタンをクリックします。
    * **[OneDrive for Business URL]** の横にある **[検出]** ボタンをクリックします。
    * フィールドにデータが入力されたら、**[変更の保存]** ボタンをもう一度クリックします。
1. **[更新]** ボタンをクリックしてインストールを確認し、**[変更の保存]** を押します。
1. 次に、Moodle サーバーと Azure Active Directory の間でユーザーを同期する必要があります。 環境に応じて、この段階でさまざまなオプションを選択できます。 ここで設定した構成は、すべてのものを同期させるために、Moodle cron を実行するたびに (通常は 1 日に 1 回) 実行されることに注意してください。開始するには、以下の手順に従います。
    * **[同期の設定] タブ**に切り替えます
    * 「**ユーザーを Azure AD と同期する**」セクションで、環境に適用されるもののチェックボックスを選択します。 通常、少なくとも次のものを選択します。
        * Azure AD のユーザーの Moodle でアカウントを作成する
        * Azure AD のユーザーの Moodle ですべてのアカウントを更新する
    * 「**ユーザー作成の制限**」セクションでは、Moodle に同期される Azure AD ユーザーを制限するフィルターを設定できます。
    * 「**ユーザーのフィールド マッピング**」セクションでは、Azure AD から Moodle ユーザー プロファイルへのフィールド マッピングをカスタマイズできます。
    * 「**Teams の同期**」セクションでは、既存の Moodle コースの一部またはすべてのグループ (つまり Teams) を自動的に作成することを選択できます。
1. cron ジョブを検証するには (最初の実行を希望する場合は手動で実行)、「**ユーザーを Azure AD と同期する**」セクションの **[スケジュールされたタスク管理ページ]** リンクをクリックします。 これにより、**[スケジュールされたタスク]** ページに移動します。
    * 下にスクロールして、**[ユーザーを Azure AD と同期する]** ジョブを探し、**[今すぐ実行]** をクリックします。
    * 既存のコースに基づいてグループを作成することを選択した場合は、**[Office 365 でユーザー グループを作成する]** ジョブも実行できます。
1. プラグイン管理ページに戻り ([サイトの管理]、[プラグイン]、[Microsoft 365 の統合] の順に移動)、**[Teams 設定]** ページを選択します。 Teams アプリの統合を有効にするには、いくつかのセキュリティ設定を構成する必要があります。
    * OpenID Connect を有効にするには、**[認証の管理]** リンクをクリックし、**OpenId Connect** 行が灰色表示されている場合は目のアイコンをクリックします。
    * 次に、フレームの埋め込みを有効にする必要があります。 **HTTP セキュリティ**リンクをクリックしてから、**[フレームの埋め込みを許可する]** の横にあるチェックボックスをクリックします。
    * 次の手順は、Moodle API 機能を有効にする Web サービスを有効にすることです。 **[高度な機能]** リンクをクリックし、**[Web サービスを有効にする]** の横のチェックボックスがオンになっていることを確認します。
    * 最後に、Microsoft 365 または Office 365 の外部サービスを有効にする必要があります。 次に、**[外部サービス]** リンクをクリックします。
        * **Moodle Office 365 Web サービス**行の **[編集]** をクリックします。
        * **[有効]** の横にあるチェックボックスをオンにして、**[変更の保存]** をクリックします
    * 次に、認証されたユーザー権限を編集して、Web サービス トークンを作成できるようにする必要があります。 **[役割「認証されたユーザー」の編集]** リンクをクリックします。 下にスクロールして、**[Web サービス トークンを作成する]** 機能を見つけ、**[許可]** チェックボックスをオンにします。

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>手順 3: Moodle アシスタント ボットを Azure に展開する

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Microsoft Teams 用の無料の Moodle アシスタント ボットは、教師と学生が Moodle のコース、課題、成績、その他の情報に関する質問に答えるのに役立ちます。 ボットはまた、Teams 内の学生と教師に Moodle の通知を送信します。 このボットは Microsoft によって管理されているオープンソース プロジェクトであり、[GitHub で利用できます](https://github.com/microsoft/Moodle-Teams-Bot)。

> [!NOTE]
> このセクションでは、リソースを Azure サブスクリプションに展開し、すべてのリソースは**無料利用**枠を使用して構成されます。 ボットの使用状況によっては、これらのリソースの拡張が必要になる場合があります。
> ボットなしで Moodle タブを使用したい場合は、[手順 4](#step-4-deploy-your-microsoft-teams-app) にスキップします。

### <a name="moodle-bot-information-flow"></a>Moodle ボットの情報フロー

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Microsoft Teams の情報フローの Moodle ボットの図" />


ボットをインストールするには、最初に [Microsoft ID プラットフォーム](https://identity.microsoft.com/Landing)にボットを登録する必要があります。 これにより、ボットは Microsoft エンドポイントに対して認証できます。 ボットを登録するには、以下の手順に従います。

1. プラグイン管理ページに戻り ([サイトの管理]、[プラグイン]、[Microsoft 365 の統合] の順に移動)、**[Teams 設定]** タブを選択します。
1. **[Microsoft アプリケーション登録ポータル]** リンクをクリックして、Microsoft ID でログインします。
1. アプリ名を入力し (例: MoodleBot)、**[作成]** ボタンをクリックします。
1. **アプリケーションの ID** をコピーして、**[Teams 設定]** ページの **[ボット アプリケーションの ID]** フィールドに貼り付けます。
1. **[新しいパスワードを生成する]** ボタンをクリックします。 生成されたパスワードをコピーして、**[Teams 設定]** ページの **[ボット アプリケーションのパスワード]** フィールドに貼り付けます。
1. フォームの一番下までスクロールし、**[変更の保存]** をクリックします。

アプリケーションの ID とパスワードを生成したので、ボットを Azure に展開します。 **[Azure に配置する]** ボタンをクリックし、必要な情報をフォームに入力します (ボット アプリケーションの ID、ボット アプリケーションのパスワード、および Moodle シークレットは **[Teams 設定]** ページにあり、Azure の情報は **[セットアップ]** ページにあります)。 フォームに入力したら、チェックボックスをクリックしてご契約条件に同意し、[**購入**] ボタンをクリックします (すべての Azure リソースが無料利用枠に展開されます)。

リソースの Azure への展開が完了したら、メッセージング エンドポイントを使用して Moodle プラグインを構成する必要があります。 まず、Azure のボットからエンドポイントを取得する必要があります。 それには、次の手順を実行します。

1. まだ行っていない場合は、[Azure ポータル](https://portal.azure.com)にログインします。
2. 左側のウィンドウで、**[リソース グループ]** を選択します。
3. リストから、ボットの展開中に使用した (または作成した) リソース グループを選択します。
4. グループ内のリソース リストから **WebApp ボット** リソースを選択します。
5. 「**概要**」セクションから**メッセージング エンドポイント**をコピーします。
6. Moodle で、Moodle プラグインの **[Teams 設定]** ページを開きます。
7. **ボットのエンドポイント** フィールドに、コピーした URL を貼り付け、*messages* という単語を *webhook* に変更します。 URL は `https://botname.azurewebsites.net/api/webhook` のようになります
8. **[変更の保存]** をクリックします。
9. 変更を保存したら、**[Teams 設定]**] タブに戻り、**[マニフェスト ファイルのダウンロード]** ボタンをクリックして、マニフェスト パッケージをコンピューターに保存します (次のセクションで使用します)。

## <a name="step-4-deploy-your-microsoft-teams-app"></a>手順 4: Microsoft Teams アプリを展開する

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

ボットを Azure に展開し、Moodle サーバーと通信するように構成したので、Microsoft Teams アプリを展開します。 これを行うには、前の手順で Moodle プラグインの [Teams 設定] ページからダウンロードしたマニフェスト ファイルを読み込みます。

アプリをインストールする前に、外部アプリとアプリのサイドロードが有効になっていることを確認する必要があります。 これを行うには、[これらの手順](https://docs.microsoft.com/MicrosoftTeams/admin-settings)に従います。 外部アプリが有効になっていることを確認したら、以下の手順に従ってアプリを展開できます。

1. Microsoft Teams を開きます。
2. ナビゲーション バーの左下にある **[ストア]** アイコンをクリックします。
3. オプションのリストから **[カスタム アプリのアップロード]** リンクをクリックします。 *注:* 全体管理者としてログインしている場合は、組織のアプリ ストアにアプリをアップロードするオプションがあります。それ以外の場合は、所属する Teams のアプリのみを読み込むことができます (「サイドロード」)。
4. 以前にダウンロードした `manifest.zip` パッケージを選択し、**[保存]** をクリックします。 マニフェスト パッケージをまだダウンロードしていない場合は、Moodle のプラグイン設定ページの **[Teams 設定]** タブからダウンロードできます。

アプリがインストールされたので、アクセスできる任意のチャネルにタブを追加できます。 これを行うには、チャネルに移動し、**+** 記号をクリックして、リストからアプリを選択します。 指示に従って、Moodle コース タブのチャネルへの追加を完了します。

手順は以上です。 あなたとあなたのチームは、Microsoft Teams から直接 Moodle コースで作業を始めることができます。

機能の要求やフィードバックを共有するには、[[ユーザーからのフィードバック] ページ](https://microsoftteams.uservoice.com/forums/916759-moodle)にアクセスしてください。
