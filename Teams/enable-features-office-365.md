---
title: 組織の Microsoft Teams の設定を管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ritikag
search.appverid: MET150
description: アプリ、外部アクセス、ゲストアクセス、Teams の設定、Teams のアップグレード設定など、あなたの組織に対する Microsoft Teams の組織全体の設定をオンまたはオフにする方法について説明します。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 596c3a3df6fc29706eea083859c65e1b1381e9ea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235350"
---
# <a name="manage-microsoft-teams-settings-for-your-organization"></a>組織の Microsoft Teams の設定を管理する

## <a name="teams-apps-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでの Teams アプリの設定

Microsoft Teams 管理センターで、**Teams アプリ**の組織向けアプリを管理します。 たとえば、組織全体または特定の Teams ユーザーが使用できるアプリを制御するポリシーを設定したり、ユーザーにとって最も重要なアプリをピン留めして Teams をカスタマイズしたりすることができます。

詳細については、「[Teams でのアプリの管理設定](admin-settings.md)」をご覧ください。  

## <a name="teams-org-wide-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでの Teams の組織全体の設定

Microsoft Teams 管理センターで、組織全体のユーザー設定を制御することができます。組織全体の設定を編集するには、Microsoft Teams 管理センターに移動して、**[Org-wide settings (組織全体の設定)]** を選択します。次の設定を構成することができます。

### <a name="external-access"></a>外部アクセス

**外部アクセス**では、Teams および Skype for Business のユーザーが、組織やドメインの外部ユーザーと通信するように設定することができます。 外部アクセスを構成するには、「[Teams のユーザーが別の Teams 組織のユーザーとチャットおよび通信できるようにする](let-your-teams-users-communicate-with-other-people.md)」を参照してください。

ドメインを追加またはブロックします。

1. [**ドメインの追加**] を選択します。
2. [ドメインの追加] ウィンドウで、ドメイン名を入力し、スペース バーをクリックして名前を保存します。
3. [**許可**] または [**禁止**]を選択します。
4. [**完了**] を選んで変更内容を保存します。 

### <a name="guest-access"></a>ゲスト アクセス

Microsoft Teams での**ゲスト アクセス**により、組織内のチームは組織外のユーザーにチームおよびチャネルへのアクセス権を付与することで、それらのユーザーと共同作業することができるようになります。Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、チーム チャット、会議、ファイルに完全なアクセス権を持つゲストとして Teams に参加することができます。詳細については、「[Guest access in Microsoft Teams (Microsoft Teams でのゲスト アクセス)](guest-access.md)」をご覧ください。

### <a name="teams-settings"></a>Teams の設定

**Teams の設定**で、電子メール統合、クラウド ストレージのオプション、Skype for Business の相互運用性、およびデバイスをセットアップすることができます。

#### <a name="email-integration"></a>電子メールの統合

この機能をオンにすると、ユーザーはチャネル電子メール アドレスを使用して、Teams のチャネルにメールを送信できるようなります。この操作は、ユーザーが所有するチームに属しているどのチャネルに対しても行えます。ユーザーのメールは、チーム メンバーに対してオンになっている追加のコネクタがあるチーム内の任意のチャネルにも送信できます。電子メール統合をオンにするには、[**Allow users to send emails to a channel email address (ユーザーがメールをチャネルの電子メール アドレスに送信できるようにする)**] が [**オン**] であることを確認します。 

#### <a name="files"></a>ファイル

ファイル共有オプションおよびファイル保存オプションをオンまたはオフにすることができます。 

ユーザーは Teams のチャネルやチャットでクラウド ストレージ サービスを介して、ファイルのアップロードや共有を行うことができます。現時点では、Teams のクラウド ストレージ オプションには、Box、Dropbox、Google ドライブ、ShareFile があります。自分の組織で使用することになるクラウド ストレージ プロバイダのスイッチをオンにします。

#### <a name="organization"></a>組織

ユーザーの組織について詳細な組織図を示す、[**組織**] タブをオンにすることができます。詳細については、「[Teams で組織タブを使用する](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894)」をご覧ください。

#### <a name="devices"></a>デバイス

これらの設定により、Microsoft Teams 会議に参加している Surface Hub デバイスのリソース アカウントの動作を制御します。これらの設定を使用して、認証の要件を構成し、コンテンツ PIN を要求し、Surface Hub リソース アカウントをオンにしてメッセージを送信します。

- **Require a secondary form of authentication to access meeting content (会議のコンテンツにアクセスするための認証のセカンダリ フォームを要求する)** – コンテンツ PIN を入力するときにユーザーが持つアクセスのレベルを選択します。
- **Set content PIN (コンテンツ PIN を設定する)** – ドキュメントに対する未承認のアクセスを防ぐためにこの PIN を入力するようにユーザーに要求します。これにより、未承認のユーザーが今後の会議に参加したり、添付ファイルを参照したりすることを防ぐことができます。
- **Resource accounts can send messages (リソース アカウントがメッセージを送信することができる)** – この設定を [**オン**] にすると、メッセージが Surface Hub リソース アカウントから送信されるようになります。

#### <a name="search-by-name"></a>名前で検索

Microsoft Teams の範囲指定ディレクトリ検索では、アドレス帳ポリシー (APB) を使用して、組織がどのように組織内のユーザーを検索するか、およびそれらのユーザーと通信するかを制御するために、仮想の境界を作成することができます。範囲指定ディレクトリ検索を使用することが考えられる状況は次のとおりです。

- 所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。 
- 所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。 

範囲指定ディレクトリ検索をオンにするには、この設定を [**オン**] に切り替えます。

### <a name="teams-upgrade"></a>Teams のアップグレード

これらの設定を使用して、自分たちのユーザーがどのように Skype for Business から Microsoft Teams にアップグレードするかを構成することができます。 

#### <a name="coexistence-mode"></a>共存モード
共存モードを指定することができます。**Teams のみ**、**アイランド** (Teams と Skype for Business が共存) または **Skype for Business のみ**を選択することができます。 選択した共存モードにより、着信通話およびチャットのルーティングと、ユーザーによってチャットや通話を開始したり会議をスケジュールしたりするために使用されるアプリが決まります。 共存モードの詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。

#### <a name="app-preferences"></a>アプリの基本設定

ユーザーが Skype for Business の会議に参加するために使用するアプリを選ぶことができます (Skype for Business または [Skype 会議アプリ](https://support.office.com/ja-JP/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5))。この設定は、共存モードの設定に依存しません。

## <a name="how-can-i-tell-which-features-are-available"></a>利用可能な機能を知る方法を教えてください。

新しい Teams の機能の詳細については、「[Microsoft 365 ロードマップ](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)」を参照してください。新機能および今後導入される機能については、Teams の「[新機能](https://support.office.com/ja-JP/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)」ページと、Teams に関する[技術コミュニティの Microsoft Teams ブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)を参照してください。 

## <a name="more-information"></a>詳細情報

管理機能を実行できる役割については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。
