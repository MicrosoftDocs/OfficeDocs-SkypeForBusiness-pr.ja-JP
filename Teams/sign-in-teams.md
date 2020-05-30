---
title: 先進認証を使用して Teams にサインインする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 先進認証のしくみ、アカウントの切り替え方法、先進認証のトラブルシューティングについて説明します。 サインイン時に、事前入力されているユーザーの名前 (UPN) を無視するように Teams に指示する方法についても説明します。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63bfd0cb9fe4292b180dfc6a0c7852b3c90a8bc4
ms.sourcegitcommit: 624bd511b96cf213483d3ea8f27b20a91d955550
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330542"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>先進認証を使用して Microsoft Teams にサインインする
==========================

Microsoft は、組織が ハイブリッド ドメイン参加構成か Azure AD 参加構成のいずれかで Windows 10 の最新バージョンを使用することを推奨しています。 これにより、Windows の Web アカウント マネージャーでユーザーのアカウントが準備され、Teams や他の Microsoft アプリケーションへのシングル サインオンが可能になります。 これにより、ユーザー エクスペリエンス (サイレント サインイン) と、セキュリティに対する姿勢を改善します。

Microsoft Teams は先進認証を使用して、サインイン操作をシンプルかつ安全なものとしています。 ユーザーが Teams にサインインする方法については、「[Teams にサインインする](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)」を参照してください。

## <a name="how-modern-authentication-works"></a>先進認証のしくみ

先進認証とは、ユーザーが資格情報 (職場のメールやパスワードなど) を既に別の場所に入力したことを Teams に知らせ、ユーザーが資格情報を再度入力することを要求されることなくアプリを起動できるようにするためのプロセスです。 ユーザーが Windows を使用しているのか Mac を使用しているのかなど、いつくかの要因によってエクスペリエンスは異なります。 また、組織で単一要素認と多要素認証のいずれが有効にされているかによってもエクスペリエンスは異なります (多要素認証では通常、電話での資格情報の確認、一意のコードの提供、PIN の入力、または拇印の提示を行う必要があります)。 以下は、それぞれの先進認証シナリオの簡単な説明です。

### <a name="windows-users"></a>Windows ユーザー

- ユーザーが自分の職場または学校アカウントを使用して既に Windows や別の Office アプリにサインインしている場合、ユーザーが Teams を起動すると、直ちにアプリに移動します。 ユーザーが資格情報を入力する必要はありません。

- Microsoft では、最高のシングル サインオン エクスペリエンスを得るために、Windows 10 のバージョン 1903 以降の使用を推奨しています。

- ユーザーが自分の職場または学校アカウントにいずれのアプリからもサインインしていない場合、ユーザーが Teams を起動すると、組織で単一要素認と多要素認証 (SFA または MFA) のどちらを求める設定になっているかにより、ユーザーはいずれかの認証を提供するよう求められます。

- ドメインに参加しているコンピューターにユーザーがサインインしている場合、ユーザーが Teams を起動すると、MFA を要求するように組織で設定されているかどうか、または、ユーザーのコンピューターへのサインインで既に MFA が要求されているのかどうかにより、もう 1 つ別の認証手順を実行するよう求められる場合があります。 コンピューターへのサインインで既に MFA が要求されている場合、ユーザーが Teams を開くとアプリが自動的に起動します。

- ドメインに参加している PC では、SSO が利用できない場合に、Teams がログイン画面にユーザー プリンシパル名 (UPN) を事前に入力しておく場合があります。 特に組織がオンプレミスと Azure Active Directory で異なる UPN を使用している場合に、これを必要としない場合もあります。 その場合には、次の Windows レジストリ キーを使用して、UPN の事前設定をオフにすることができます。

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > 「.local」 または 「.corp」 で終わるユーザー名については、ユーザー名の事前入力のスキップは既定でオンになっているため、レジストリ キーを設定してオフにする必要はありません。


### <a name="mac-users"></a>Mac ユーザー

MacOS 上では、Teams はユーザーにユーザー名と資格情報の入力を促し、組織の設定によっては多要素認証を促す場合もあります。 ユーザーが資格情報を入力すると、入力を再度求められることはありません。 これ以降、ユーザーが同じコンピューターで作業している場合は常に、Teams が自動的に起動します。

## <a name="switching-accounts-after-completing-modern-authentication"></a>先進認証を行った後のアカウントの切り替え

ドメインに参加しているコンピューターでユーザーが作業している場合 (テナントで Kerberos が有効になっている場合など)、先進認証を行った後は、ユーザーはアカウントを切り替えることはできません。 ユーザーが作業を行っているのはドメインに参加しているコンピューターではない場合、ユーザーはアカウントを切り替えることができます。

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>先進認証を行った後に Teams からサインアウトする

Teams からサインアウトするには、アプリの上部にある自分のプロファイル画像をクリックし、[**サインアウト**] を選択します。タスク バーにあるアプリのアイコンを右クリックして [**ログアウト**] を選択することもできます。一旦 Teams からサインアウトすると、アプリを起動するには資格情報をもう一度入力する必要があります。

## <a name="urls-and-ip-address-ranges"></a>URL と IP アドレスの範囲

Teams を使用するには、インターネットへの接続が必要です。 Office 365 の各プラン、政府機関向けまたはその他のクラウドを使用するユーザーが到達可能である必要があるエンドポイントについては、「[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)」を参照してください。

> [!IMPORTANT]
> Teams では現在、すべてのユーザーについて、Google の ssl.gstatic.com サービス (<https://ssl.gstatic.com)> への接続 (TCP ポート 443) が要求されています。Gstatic を使用していない場合であってもこれは要求されます。 Teams では間もなく (2020 年前半) この要件が削除される予定になっており、そのタイミングに合わせてこの記事も更新されます。

## <a name="troubleshooting-modern-authentication"></a>先進認証のトラブルシューティング

先進認証は Office を使用しているすべての組織で利用可能であるため、もしユーザーがこのプロセスを完了できない場合には、組織のドメインまたは組織の職場または学校アカウントに何らかの問題がある可能性があります。

詳細については、「[Microsoft Teams へのサインインで問題が発生する理由](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)」を参照してください。
