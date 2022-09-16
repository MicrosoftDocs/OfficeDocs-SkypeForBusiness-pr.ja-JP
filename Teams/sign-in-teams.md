---
title: サインインの制限やサインインの動作など、さまざまなテクノロジが Microsoft Teams のサインオンに与える影響。
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: シングル サインオンや先進認証などのテクノロジが、iOS、Android、macOS、PC でのサインイン動作にどのように影響するかを説明します。 多くのアカウントを持つチームを使用し、サインインを制限する方法。 サインイン時に、事前入力されているユーザーの名前 (UPN) を無視するように Teams に指示する方法についても説明します。
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c37d9fd2140aaae9ccce443c81c537dcfb92305e
ms.sourcegitcommit: 0181a62c8d5a3f5b28fbb5a15645f0e82a1b8f35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2022
ms.locfileid: "67734611"
---
# <a name="how-different-technologies-effect-microsoft-teams-sign-on"></a>さまざまなテクノロジが Microsoft Teams のサインオンに与える影響

シングル サインオン (SSO)、先進認証 (MS)、多要素認証 (MA) などのテクノロジがユーザーのサインインエクスペリエンスにどのような影響を与えるかを理解する必要がある場合、この記事は、ユーザーと管理者が期待できる表示内容を明確にするのに役立ちます。 また、macOS、android、および iOS デバイスのログイン動作、複数のアカウントを使用したログインのしくみ、ログイン画面で自動的に入力された資格情報または "事前入力" を削除する方法、およびサインオンを制限する方法についても説明します。

ログイン中に Microsoft Team の予想される動作をロールで把握する必要がある場合は、この記事をブックマークします。

## <a name="microsoft-teams-and-windows-users-sign-in-recommendations"></a>Microsoft Teams と Windows ユーザー: サインインに関する推奨事項

Microsoft は、組織が ハイブリッド ドメイン参加構成か Azure AD 参加構成のいずれかで Windows 10 の最新バージョンを使用することを推奨しています。 最新バージョンの使用によって、Windows の Web アカウント マネージャーでユーザーのアカウントが準備され、Teams や他の Microsoft アプリケーションへのシングル サインオンが可能になります。 シングルサインオンにより、ユーザー エクスペリエンス (サイレント サインイン) と、セキュリティ対策が改善されます。

Microsoft Teams は先進認証を使用して、サインイン操作をシンプルかつ安全なものとしています。 ユーザーが Teams にサインインする方法については、「[Teams にサインインする](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)」を参照してください。

### <a name="how-modern-authentication-ma-effects-your-sign-in-what-users-will-see-when-ma-is-on"></a>先進認証 (MA) がサインインに及ぼす影響: MA がオンのときにユーザーに表示される内容

先進認証は、他の場所でユーザーが既に資格情報 (職場のメールやパスワードなど) を入力していることを Teams に知らせるプロセスの一部であり、アプリを起動するためにもう一度入力する必要はありません。 エクスペリエンスは、ユーザーが Windows オペレーティング システムや Mac で作業している場合など、いくつかの要因によって異なります。

サインインの動作は、組織が単一要素認証または多要素認証を有効にしているかどうかによっても異なります。 多要素認証を使用するには通常、電話による資格情報の確認、固有のコードの提供、PIN の入力、拇印の提示が含まれます。 

先進認証は、Teams を使用するすべての組織で使用できます。 ユーザーがプロセスを完了できない場合は、組織の Azure AD 構成に根底の問題がある可能性があります。 詳細については、「[Microsoft Teams へのサインインで問題が発生する理由](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)」を参照してください。

ここでは、各最新の認証シナリオでユーザーが期待できる動作の概要を示します。

- ユーザーが自分の職場または学校アカウントを使用して、すでに Windows や別の Office アプリにサインインしている場合、ユーザーが Teams を起動すると、直ちにアプリに移動します。資格情報の入力は不要です。

- Microsoft では、最高のシングル サインオン エクスペリエンスを得るために、Windows 10 のバージョン 1903 以降の使用を推奨しています。

- ユーザーが自分の Microsoft の職場または学校アカウントにどこからもサインインしていない場合、ユーザーが Teams を起動すると、ユーザーは単一要素認証または多要素認証 (SFA または MFA) のいずれかの認証を提供するよう求められます。このプロセスは、組織がどの方法を認証時に要求すると決めているかに依ります。

- ドメインに参加しているコンピューターにユーザーがサインインして、Teams を起動すると、MFA を要求するように組織で選択しているか、またはコンピューターへのサインインで既に MFA が要求されているかにより、もう 1 つ追加の認証手順を実行するよう求められる場合があります。

- ドメインに参加している PC では、SSO が不可能な場合、Teams はログイン画面にユーザー プリンシパル名 (UPN) を事前入力できます。 特に組織がオンプレミスと Azure Active Directory で異なる UPN を使用している場合に、これを必要としない場合もあります。 このような場合は、 **次の Windows レジストリ キーを使用して UPN の事前作成を無効にすることができます**。

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > 「.local」 または 「.corp」 で終わるユーザー名については、ユーザー名の事前入力のスキップは既定でオンになっているため、レジストリ キーを設定してオフにする必要はありません。

### <a name="microsoft-teams-sign-on-to-another-account-on-a-domain-joined-computer"></a>Microsoft Teams がドメイン参加済みコンピューター上の別のアカウントにサインオンする

ドメインに参加しているコンピューターのユーザーが、同じ Active Directory ドメイン内の別のアカウントを使用して Teams にサイン インできない場合があります。

## <a name="macos-users-and-microsoft-teams-sign-on-prompts"></a>macOS ユーザーと Microsoft Teams のサインオン プロンプト

MacOS 上では、Teams はユーザーにユーザー名と資格情報の入力を促し、組織の設定によっては多要素認証を促す場合もあります。 ユーザーが資格情報を入力すると、入力を再度求められることはありません。 これ以降、ユーザーが同じコンピューターで作業している場合は常に、Teams が自動的に起動します。

## <a name="microsoft-teams-sign-on-for-ios-and-android-users"></a>iOS および Android ユーザー向けの Microsoft Teams のサインオン

サインインすると、モバイルユーザーには、デバイス上で現在サインインしているまたは以前にサインインしたすべての Microsoft 365 アカウントの一覧が表示されます。 ユーザーは、任意のアカウントをタップしてサインインできます。 モバイル サインインには2つのシナリオがあります:

1. 選択されたアカウントが他の Office 365 または Microsoft 365 アプリに現在サインインしている場合、そのユーザーは直接 Teams に移動します。ユーザーは資格情報を入力する必要はありません。

2. ユーザーが他の場所で Microsoft 365 アカウントにサインインしていない場合は、組織がモバイル サインイン ポリシー用に構成した内容に応じて、単一要素認証または多要素認証 (SFA または MFA) を提供するように求められます。

> [!NOTE]
> ユーザーがこのセクションで説明するサインオン エクスペリエンスを体験するには、デバイスで iOS バージョン 2.0.13 (ビルド 2020061704) 以降の Teams、または Android バージョン 1416/1.0.0.2020061702 以降の Teams を実行している必要があります。

## <a name="using-microsoft-teams-with-multiple-sign-in-accounts"></a>複数のサインイン アカウントで Microsoft Teams を使用する

IOS と Android の Teams では、複数の仕事用または学校用、および複数の個人用アカウントを並べて使うことができます。 Teams のデスクトップ  アプリケーションでは1 つの職場または学校のアカウントと 1 つの個人用のアカウントが2020 年 12 月にはサポートされていますが、後日複数の職場/学校のアカウントをサポートできるようになります。

次の画像は、ユーザーが複数のアカウントを Teams モバイル アプリケーション に追加する方法を示しています。

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Teams で複数のアカウントを追加します。":::

## <a name="restrict-sign-in-to-microsoft-teams"></a>Microsoft Teams へのサインインを制限する

組織は、組織が承認したアプリケーションを管理されたデバイで使用する方法を制限しようとする場合があります。たとえば、学生や従業員が他の組織のデータにアクセスするのを制限したり、組織が承認したアプリを個人の目的で使用するのを制限できるようにする場合があります。 これらの制限は、Teams アプリケーションが認識するデバイスポリシーを設定することによって設定できます。

### <a name="how-to-restrict-microsoft-teams-sign-in-on-mobile-devices"></a>モバイル デバイスで Microsoft Teams のサインインを制限する方法

iOS と Android の Teams は、IT 管理者に、アカウント構成を Microsoft 365 アカウントに配布する機能を提供します。 この機能は、iOS の[管理対象アプリ構成](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) チャネルまたは Android の[Android Enterprise](https://developer.android.com/work/managed-configurations) チャネルを使用するすべてのモバイル デバイス管理 （MDM）プロバイダーで機能します。

Microsoft Intune に登録されているユーザーは、Azure Portal の Intune を使用してアカウント構成設定を展開できます。

MDM プロバイダーでアカウント セットアップ構成が構成され、ユーザーがデバイスを登録した後、iOS と Android の Teams は、許可されたアカウントのみ Teams サインイン ページに表示します。ユーザーはこのページで許可されているアカウントをタップして、サインインできます。

管理対象デバイスの Azure Intune ポータルで次の構成パラメーターを設定します。

|プラットフォーム |キー  |値  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **有効**: 使用できるアカウントは、IntuneMAMUPN キーで定義された管理対象ユーザー アカウントのみです。<br> **無効** (または、大文字と小文字を区別しない **有効** な任意の値): すべてのアカウントを使用できます。        |
|iOS     |   **IntuneMAMUPN**      |   Teams. へのサインインが許可されているアカウントの UPN です。<br> Intune に登録されているデバイスの場合、{{userprincipalname}} トークンを使用して、登録済みのユーザーアカウントを表すことができます。       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    このキーで定義された管理対象ユーザーアカウントのみ許可されます。<br> 1 つ以上のセミコロン;]- 区切られた UPNs。<br> Intune に登録されているデバイスの場合、{{userprincipalname}} トークンを使用して、登録済みのユーザーアカウントを表すことができます。

アカウント セットアップ構成が設定されると、Teams はサインイン機能を制限し、登録されたデバイス上の許可されたアカウントのみにアクセスを許可します。

管理対象の iOS/iPadOS デバイスのアプリ構成ポリシーを作成するには、「[管理対象の iOS/iPadOS デバイスのアプリ構成ポリシーの追加](/mem/intune/apps/app-configuration-policies-use-ios)」を参照してください。

管理対象の Android デバイスのアプリ構成ポリシーを作成するには、「[管理対象の Android デバイスのアプリ構成ポリシーの追加](/mem/intune/apps/app-configuration-policies-use-android)」を参照してください。

### <a name="how-to-restrict-teams-sign-in-on-desktop-devices"></a>デスクトップ デバイスで Teams のサインインを制限する方法

Windows および macOS 上の Microsoft Teams アプリでは、組織へのサインインを制限するデバイス ポリシーのサポートが強化されています。 ポリシーは、MDM (モバイル デバイス管理) や GPO (グループ ポリシー オブジェクト) などの通常のデバイス管理ソリューションで設定できます。

このポリシーがデバイスに構成されている場合、ユーザーは、ポリシーで定義されている "テナントの許可リスト" に含まれている Azure AD テナントを使用しているアカウントでのみサインインできます。 ポリシーは、最初のアカウントと追加のアカウントを含むすべてのサイン インに適用されます。 組織が複数の Azure AD テナントにまたがる場合、許可リストに複数のテナント ID を含めることができます。 別のアカウントを追加するためのリンクは、引き続き Teams アプリに表示される場合がありますが、操作はできません。

> [!NOTE]
> 
>1. ポリシーは、サインインのみ制約します。他の Azure AD テナントにユーザーがゲストとして招待される機能や、そこでそのテナント (ユーザーはゲストとして招待されている) への切り替えが制限されることはありません。
>2. このポリシーには Windows バージョン 1.3.00.30866 以降の Teams および MacOS バージョン 1.3.00.30882 (2020 年 11 月半ばにリリースされました) の Teams が必要です。

**Windows 管理用テンプレート ファイル (ADMX/ADML) のポリシー** は、[ダウンロード センター](https://www.microsoft.com/download/details.aspx?id=49030)から利用できます (管理テンプレート ファイルを説明する名前は、「特定のテナントのアカウントの Teams へのサインインを制限する」です)。Windows レジストリに手動でキーを設定することもできます。

- 値の名前: RestrictTeamsSignInToAccountsFromTenantList
- 値の種類: 文字列
- 値のデータ: テナント ID またはコンマ区切りのテナント ID のリスト
- パス: 次のいずれかを使用します。

 Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams

例: ソフトウェア\ポリシー\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = テナント ID またはソフトウェア\ポリシー\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = テナント ID 1、テナント ID 2、テナント ID 3

**MacOS のポリシー** MacOS に管理されているデバイスは、.plist を使用して、サインイン制限を展開します。 構成プロファイルは、(優先順位の名前を示す) キーによって識別されたエントリで構成される .plist ファイルです。その後に、基本設定の性質に応じて、値が表示されます。 値には、単純 (数値など) または複合のいずれかを指定できます。たとえば、基本設定の入れ子リストがあります。

- ドメイン: com.microsoft.teams
- キー: RestrictTeamsSignInToAccountsFromTenantList
- データ型: 文字列
- コメント: Azure AD テナント ID のコンマ区切りのリストを入力します。

### <a name="global-sign-in-and-microsoft-teams"></a>グローバル サインインと Microsoft Teams

Teams Android アプリは、グローバルなサインインとサインアウトをサポートするようになり、現場担当者は手間なくサインインとサインアウトができるようになりました。 従業員は、共有デバイスプールからデバイスを選択し、1回サインインするだけで、シフト中は"自分のものにする" ということができます。 これらのユーザーは、シフトの最後に、サインアウトすると、デバイスに対してグローバルにサイン アウトできます。 詳細については、[「Teams をサインアウトする」](sign-out-of-teams.md)を参照してください。 これにより、デバイスから個人情報と会社情報がすべて削除され、デバイスがデバイスプールに返されます。 この機能を利用するには、デバイスを shared モードにする必要があります。 サインアウトする前に、アクティブな会議を終了するか、デバイスに電話をかけてください。共有デバイスの設定方法については、「[Android で共有デバイス モードを使用する方法](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode)」をご覧ください。

サインインエクスペリエンスは、Teams の標準的なサインイン操作と似ています。

## <a name="urls-and-ip-address-ranges-for-microsoft-teams"></a>Microsoft Teams の URL と IP アドレス範囲

Teams を使用するには、インターネットへの接続が必要です。Office 365 の各プラン、政府機関向けまたはその他のクラウド用の Teams を使用するユーザーが到達可能なエンドポイントについては、「[Office 365 の URL と IP アドレスの範囲](/office365/enterprise/urls-and-ip-address-ranges)」を参照してください。


## <a name="related-topics"></a>関連項目

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)
