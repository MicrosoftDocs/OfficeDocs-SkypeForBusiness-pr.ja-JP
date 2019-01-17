---
title: Office 365 を使用する組織で Microsoft Teams の機能を管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Office 365 を使用する組織での、タブ、コネクタ、ボット、またはそれらの組み合わせを含む、Microsoft Teams のアプリをオンまたはオフに切り替える方法について説明します。
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 383a4a18d466e367a31e4b99f9975b51cc5f559a
ms.sourcegitcommit: 42083a67ad92d81643131c8514d82c529a1ac491
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2019
ms.locfileid: "27988187"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Office 365 を使用する組織で Microsoft Teams の機能を管理する

すべての Teams の設定は、新しい Microsoft Teams および Skype for Business 管理センターに間もなく移行されます。Teams の機能のうち、アプリのみが Office 365 管理センターで管理されます。 

特に明記されていない限り、オプションの既定値は [**オン**] です。

## <a name="tenant-wide-settings"></a>テナント全体の設定 

Microsoft 365 管理センターの [**テナント全体の設定**] で Teams のアプリをオフにしたりオンにしたりすることができます。 

Teams の [**テナント全体の設定**] を編集するには、Microsoft 365 管理センターに移動して、[**設定**]  >  [**サービスとアドイン**]  >  [**Microsoft Teams**] の順に選択します。Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。 

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>アプリ

アプリは、Teams (ファーストパーティ アプリ、または既定のアプリ) によって、またはサードパーティ (外部アプリ) によって提供される、タブ、コネクタ、ボットまたはそれらの 3 つを任意に組み合わせたのものです。 [**アプリ**] の下で、既定のアプリを有効または無効にしたり、外部アプリを制御する設定を構成したりすることができます。  

#### <a name="default-apps"></a>既定のアプリ

プランナー、称賛、天気などのアプリは、Teams によって提供されます。 アプリをオンにするには、そのアプリのチェック ボックスを選択します。 アプリをオフにするには、チェック ボックスをクリアします。 

![[既定のアプリ] セクションのスクリーン ショット。](media/teams-tenant-wide-settings-default-apps.png "[既定のアプリ] セクションのスクリーン ショット")

#### <a name="external-apps"></a>外部アプリ

これらのアプリはサードパーティによって提供されます。 外部アプリについては、次の設定を構成することができます。

![[外部アプリ] セクションのスクリーンショット。](media/teams-tenant-wide-settings-external-apps-settings.png "[外部アプリ] セクションのスクリーンショット。オンまたはオフにすることができる設定")

- **Microsoft Teams の外部アプリを許可する**: この設定がオンになると、ユーザーは自分の組織で利用できる外部アプリを追加することができます。 

- **既定で新しい外部アプリを有効にする**: この設定がオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されると、それらをすぐにアクティブ化することができます。 新しいアプリに対する制御を行う場合はこの設定をオフにします。 これをオフにする場合は、自分の組織で新しいアプリを利用する機会を失うことがないように、新しいアプリについて定期的に確認するようにする必要があります。 

- **外部アプリのサイドローディングを利用できるようになります**:一部の外部アプリをオンにして、その他のアプリをオフにする場合は、この設定をオフにしてから、外部アプリのリストでユーザーがアクセスしないようするアプリをオフにします。 この設定がオンになっているときは、アクセス権が付与されているチーム所有者およびメンバーは、アプリを Teams にサイドリーディングすることができます。 

詳細については、「[Teams でのアプリの管理設定](admin-settings.md)」をご覧ください。 

## <a name="teams-org-wide-settings"></a>Teams の組織全体の設定

Microsoft Teams および Skype for Business 管理センターで組織全体のユーザー設定を制御することができます。 組織全体の設定を編集するには、Microsoft Teams および Skype for Business 管理センターに移動して、[**Org-wide settings (組織全体の設定)**] を選択します。 次の設定を構成することができます。

### <a name="external-access"></a>外部アクセス

**外部アクセス**では、Teams および Skype for Business のユーザーが、組織の外部ユーザーと通信するように設定することができます。外部アクセスを構成するには、[[Let your Teams users chat and communicate with users in another Teams organization (Teams ユーザーが別の Teams の組織に所属するユーザーと通信することを許可する) ](let-your-teams-users-communicate-with-other-people.md)] に移動します。

### <a name="guest-access"></a>ゲスト アクセス

Microsoft Teams での**ゲスト アクセス**により、組織内のチームは組織外のユーザーにチームおよびチャネルへのアクセス権を付与することで、それらのユーザーと共同作業することができるようになります。Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、チーム チャット、会議、ファイルに完全なアクセス権を持つゲストとして Teams に参加することができます。詳細については、「[Guest access in Microsoft Teams (Microsoft Teams でのゲスト アクセス)](guest-access.md)」をご覧ください。

### <a name="teams-settings"></a>Teams の設定

**Teams の設定**で、電子メール統合、クラウド ストレージのオプション、Skype for Business の相互運用性、およびデバイスをセットアップすることができます。

#### <a name="email-integration"></a>電子メール統合

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

#### <a name="search"></a>検索

Microsoft Teams の範囲指定ディレクトリ検索では、アドレス帳ポリシー (APB) を使用して、組織がどのように組織内のユーザーを検索するか、およびそれらのユーザーと通信するかを制御するために、仮想の境界を作成することができます。範囲指定ディレクトリ検索を使用することが考えられる状況は次のとおりです。

- 所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。 
- 所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。 

範囲指定ディレクトリ検索をオンにするには、この設定を [**オン**] に切り替えます。

### <a name="teams-upgrade"></a>Teams のアップグレード

これらの設定を使用して、自分たちのユーザーがどのように Skype for Business から Microsoft Teams にアップグレードするかを構成することができます。 

#### <a name="coexistence-mode"></a>共存モード
共存モードを指定することができます。**Teams のみ**、**Islands (アイランド)** (Teams と Skype for Business が共存) または **Skype for Business のみ**を選択することができます。選択した共存モードにより、着信通話およびチャットのルーティングと、ユーザーによってチャットや通話を開始したり会議をスケジュールするために使用されるアプリが決まります。Teams と Skype for Business との相互運用性については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md)」をご覧ください。

#### <a name="app-preferences"></a>アプリの基本設定

ユーザーが Skype for Business の会議に参加するために使用するアプリを選ぶことができます (Skype for Business または [Skype 会議アプリ](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5))。この設定は、共存モードの設定に依存しません。

## <a name="how-can-i-tell-which-features-are-available"></a>利用可能な機能を知る方法を教えてください。

新しい Teams の機能の詳細については、[Office 365 ロードマップ](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams)をご覧ください。新機能および今後導入される機能については、Teams の[新機能](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US)ページと、Teams に関する[技術コミュニティの Microsoft Teams ブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531)をご覧ください。 

## <a name="more-information"></a>詳細情報

管理機能を実行できる役割については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」をご覧ください。
