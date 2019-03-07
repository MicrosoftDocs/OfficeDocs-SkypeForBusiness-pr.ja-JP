---
title: 先進認証を使用して Microsoft Teams にサインインする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 現代の認証を使用して、マイクロソフトのチームにサインインする方法です。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eec164da4dafe9be54272a72680cfa920d32d60c
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458813"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>先進認証を使用して Microsoft Teams にサインインする
==========================

マイクロソフトのチームでは、現代の認証を使用して、シンプルかつセキュリティで保護されたサインイン処理をしてください。 ユーザーがチームにサインインする方法を表示するには、[チームへのサインイン](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)を参照してください。

## <a name="how-modern-authentication-works"></a>現在の認証のしくみ

現代の認証は、ユーザー既に入力されている資格情報 (と同様に自分の仕事の電子メールとパスワードを使用して) 別の場所で、し、アプリケーションを起動するには、もう一度入力して必要なされるべきではないことを知っているチームをできるようにするプロセスです。 経験によって異なりますいくつかの要因のようなユーザーは、windows、または、mac 上に作業している場合 一元的認証方式、または複数要素の認証、組織が有効になっているかどうかによっても異なります (通常多要素認証では、PIN を入力する、一意のコードを提供する、携帯電話経由で資格情報を確認する必要がありますか拇印を表示) します。 ここでは、最新の認証シナリオの概要を示してします。

### <a name="windows-users"></a>Windows ユーザー: 

- ユーザーが既に署名されている場合、Office 365 のエンタープライズのアカウントでは、他の Office アプリケーションをアプリケーションに直接、撮影しているチームを起動するとき。 自分の資格情報を入力するために必要はありません。

- によってどのようなことになりましたかの一元的か、多要素認証 SFA (MFA)、表示された場合、ユーザー、署名のない Office 365 のエンタープライズ アカウントをそれ以外の場所にチームを起動するとき、伴うプロセスです。

- ユーザーは署名されている場合ドメインに参加しているコンピューターでは、チーム、MFA を必要とする組織を選択するかどうかによって、複数の認証手順のいずれかを移動することが求められる場合が、またはかどうかは、コンピューターが必要ですにサインインするのには MFA を起動したとき。 自分のコンピューターでは、既にサインインして MFA を必要とすると開くチーム、アプリケーションを自動的に開始されます。

### <a name="mac-users"></a>Mac ユーザー 

ユーザーは、チームを開始するときに自分のコンピューターから Office 365 のエンタープライズ アカウントまたはその他の Office アプリケーションのいずれかの資格情報を取得することはできません。 代わりに、(組織の設定) によって SFA や MFA を要求するメッセージが表示されます。 ユーザーが資格情報を入力するとは、再度説明する必要はありません。 その時点から、チームが自動的に開始される同じコンピューターで作業するときに。

## <a name="switching-accounts-after-completing-modern-authentication"></a>現代の認証が完了した後、アカウントを切り替える

ユーザーがドメインに参加しているコンピューター (たとえば、そのテナントが Kerberos を有効にしている場合) で作業している場合、完了した最新の認証ユーザー アカウントの切り替え、ことはできません。 ユーザーがドメインに参加しているコンピューターで動作しない場合は、アカウントに切り替えることができます。

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>現代の認証が完了した後、マイクロソフトのチームが署名

チームからサインインすると、ユーザーが、アプリの上部にある自分のプロファイル画像をクリックし、**サインアウト**を選択します。アプリケーションのタスク バーにアイコンを右クリックしても、**ログアウト**を選択します。チームのサインアウトをしているアプリケーションを起動するには、再度資格情報を入力するのには、必要があります。

## <a name="troubleshooting-modern-authentication"></a>現代の認証のトラブルシューティング

現代の認証は、チームを使用して、ユーザーがプロセスを完了することがない場合されること、ドメインまたは組織の Office 365 のエンタープライズ ・ アカウントに問題があるすべての組織で使用できます。 

詳細についてを参照してください[マイクロソフトのチームへのサインインに問題が生じる理由ですか?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)です。

