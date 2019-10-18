---
title: 先進認証を使用して Microsoft Teams にサインインする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 先進認証を使用して Microsoft Teams にサインインする方法について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5698058cbfecd62f92cfe9f198657f7c280deff
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563123"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>先進認証を使用して Microsoft Teams にサインインする
==========================

Microsoft Teams は先進認証を使用して、サインインエクスペリエンスをシンプルかつ安全な状態に保ちます。 ユーザーがチームにサインインする方法を確認するには、「 [teams にサインイン](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)する」を参照してください。

## <a name="how-modern-authentication-works"></a>先進認証のしくみ

先進認証とは、ユーザーが既に資格情報 (仕事用のメールとパスワードなど) を別の場所に入力したことをチームに知らせるプロセスであり、アプリを開始するために再度入力する必要はありません。 エクスペリエンスは、ユーザーが Windows または Mac で作業している場合など、いくつかの要因によって異なります。 また、組織が単一要素認証を有効にしているか、多要素認証を有効にしているかによっても異なります (多要素認証では、通常、電話で資格情報を確認したり、固有のコードを提供したり、PIN を入力したりする必要があります)。拇印の提示。 最新の認証シナリオの概要を示します。

### <a name="windows-users"></a>Windows ユーザー: 

- ユーザーが Office 365 エンタープライズアカウントを使用して他の Office アプリに既にサインインしている場合、チームを起動すると、そのアプリに直接移動します。 資格情報を入力する必要はありません。

- ユーザーが自分の Office 365 Enterprise アカウントにサインインしていない場合、そのユーザーが Teams を開始すると、組織での決定に応じて、単一要素認証または多要素認証 (SFA または MFA) を提供するように求められます。処理を行います。

- ユーザーがドメインに参加しているコンピューターにサインインしている場合、Teams を開始すると、組織で MFA を要求するか、またはコンピューターで既に MFA を要求しているかどうかによって、もう1つの認証手順を実行するように求められる場合があります。 お客様のコンピューターに、サインインのために既に MFA が必要な場合は、チームを開くときにアプリが自動的に起動します。

### <a name="mac-users"></a>Mac ユーザー 

ユーザーが Teams を開始すると、そのコンピューターは、Office 365 エンタープライズアカウントまたは他の Office アプリケーションから資格情報を取得することはできません。 代わりに、組織の設定に応じて、SFA または MFA の入力を求めるプロンプトが表示されます。 ユーザーが資格情報を入力すると、もう一度提供する必要はありません。 この時点で、チームは同じコンピューターで作業しているときに自動的に開始されます。

## <a name="switching-accounts-after-completing-modern-authentication"></a>先進認証が完了した後でアカウントを切り替える

ユーザーがドメインに参加しているコンピューターで作業している場合 (たとえば、テナントが Kerberos を有効にしている場合)、先進認証を完了した後でユーザーアカウントを切り替えることはできません。 ドメインに参加しているコンピューターでユーザーが作業していない場合は、アカウントを切り替えることができます。

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>先進認証が完了した後に Microsoft Teams からサインアウトする
Teams からサインアウトするには、アプリの上部にあるプロフィール写真をクリックして、[**サインアウト**] を選択します。また、タスクバーのアプリアイコンを右クリックし、[**ログアウト**] を選択することもできます。チームからサインアウトすると、アプリを起動するために資格情報を再入力する必要があります。

## <a name="troubleshooting-modern-authentication"></a>先進認証のトラブルシューティング

新しい認証は Teams を使用するすべての組織で利用できます。そのため、ユーザーが処理を完了できない場合は、自分のドメインまたは組織の Office 365 エンタープライズアカウントに問題がある可能性があります。 

詳細については、「 [Microsoft Teams へのサインインで問題が発生するのはなぜですか?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)」を参照してください。

