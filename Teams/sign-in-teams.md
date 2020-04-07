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
description: 先進認証を使用して Microsoft Teams にサインインする方法。 Windows に UPN を無視するように設定することで、ユーザーがサインインしたときに自動的に UPN のユーザー名の追加をスキップする方法が含まれています。
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5e61b1cb79b7c4e2989d823af2c6617337291cf6
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43138896"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>先進認証を使用して Microsoft Teams にサインインする
==========================

Microsoft Teams は先進認証を使用して、サインイン操作をシンプルかつ安全なものとしています。 ユーザーが Teams にサインインする方法については、「[Teams にサインインする](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)」を参照してください。

## <a name="how-modern-authentication-works"></a>先進認証のしくみ

先進認証とは、ユーザーが資格情報 (職場のメールやパスワードなど) を既に別の場所に入力したことを Teams に知らせ、ユーザーが資格情報を再度入力することを要求されることなくアプリを起動できるようにするためのプロセスです。 ユーザーが Windows を使用しているのか Mac を使用しているのかなど、いつくかの要因によってエクスペリエンスは異なります。 また、組織で単一要素認と多要素認証のいずれが有効にされているかによってもエクスペリエンスは異なります (多要素認証では通常、電話での資格情報の確認、一意のコードの提供、PIN の入力、または拇印の提示を行う必要があります)。 以下は、それぞれの先進認証シナリオの簡単な説明です。

### <a name="windows-users"></a>Windows ユーザー 

- ユーザーが自分の Office 365 Enterprise アカウントを使用して既に別の Office アプリにサインインしている場合、ユーザーが Teams を起動すると、直ちにアプリに移動します。 ユーザーは資格情報を入力する必要はありません。

- ユーザーが自分の Office 365 Enterprise アカウントにいずれのアプリからもサインインしていない場合、ユーザーがチームを開始すると、組織で単一要素認と多要素認証 (SFA または MFA) のどちらを求める設定になっているかにより、ユーザーはいずれかの認証を提供するよう求められます。

- ドメインに参加しているコンピューターにユーザーがサインインしている場合、ユーザーが Teams を起動すると、MFA を要求するように組織で設定されているかどうか、または、ユーザーのコンピューターへのサインインで既に MFA が要求されているのかどうかにより、もう 1 つ別の認証手順を実行するよう求められる場合があります。 コンピューターへのサインインで既に MFA が要求されている場合、ユーザーが Teams を開くとアプリが自動的に起動します。

- ドメインに参加しているコンピューターにユーザーがサインインしている場合に、**Teams のサインイン画面にユーザー名を事前入力させたくない場合**は、管理者は次の Windows レジストリを設定してユーザー名 (UPN) の事前入力を無効にできます。

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > 「.local」 または 「.corp」 で終わるユーザー名については、ユーザー名の事前入力のスキップは既定でオンになっているため、レジストリ キーを設定してオフにする必要はありません。 


### <a name="mac-users"></a>Mac ユーザー 

ユーザーが Teams を起動するとき、ユーザーのコンピューターでは Office 365 Enterprise アカウントまたはユーザーのいずれの他の Office アプリケーションからも資格情報を取得できません。 代わりに、(組織の設定に応じて) SFA または MFA を求めるメッセージがユーザーに表示されます。 ユーザーが資格情報を入力すると、入力を再度求められることはありません。 これ以降、ユーザーが同じコンピューターで作業している場合は常に、Teams が自動的に起動します。

## <a name="switching-accounts-after-completing-modern-authentication"></a>先進認証を行った後のアカウントの切り替え

ドメインに参加しているコンピューターでユーザーが作業している場合 (テナントで Kerberos が有効になっている場合など)、先進認証を行った後は、ユーザーはアカウントを切り替えることはできません。 ユーザーが作業を行っているのはドメインに参加しているコンピューターではない場合、ユーザーはアカウントを切り替えることができます。

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>先進認証を行った後に Teams からサインアウトする
Teams からサインアウトするには、アプリの上部にある自分のプロファイル画像をクリックし、[**サインアウト**] を選択します。タスク バーにあるアプリのアイコンを右クリックして [**ログアウト**] を選択することもできます。一旦 Teams からサインアウトすると、アプリを起動するには資格情報をもう一度入力する必要があります。

## <a name="urls-and-ip-address-ranges"></a>URL と IP アドレスの範囲
Teams を使用するには、インターネットへの接続が必要です。 Office 365 の各プラン、政府機関向けまたはその他のクラウドを使用するユーザーが到達可能である必要があるエンドポイントについては、「[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)」を参照してください。 

> [!IMPORTANT]
> Teams では現在、すべてのユーザーについて、Google の ssl.gstatic.com サービス (https://ssl.gstatic.com) への接続 (TCP ポート 443) が要求されています。Gstatic を使用していない場合であってもこれは要求されます。 Teams では間もなく (2020 年前半) この要件が削除される予定になっており、そのタイミングに合わせてこの記事も更新されます。

## <a name="troubleshooting-modern-authentication"></a>先進認証のトラブルシューティング

先進認証は Office を使用しているすべての組織で利用可能であるため、もしユーザーがこのプロセスを完了できない場合は、組織のドメインまたは組織の Office 365 Enterprise アカウントに何か問題がある可能性があります。 

詳細については、「[Microsoft Teams へのサインインで問題が発生する理由](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)」を参照してください。

