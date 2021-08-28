---
title: Microsoft Teams からサインアウトする
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: sbhatta
description: Microsoft Teams からサインアウトする方法について説明します。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e1a81b4114814003a2d9c6ac7b41649fe34f8f1
ms.sourcegitcommit: 3cc2da11aac1a3a7d620810c6f22a7192e4ab993
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "58483207"
---
# <a name="sign-out-of-microsoft-teams"></a>Microsoft Teams からサインアウトする

ユーザーがチャット、着信通話、その他のアクティビティを引き続き受信したい場合は、Microsoft Teams アプリにサインインしたままにすることをお勧めします。 いくつかの理由のために、ユーザーが、 Teams アプリケーションからサインアウトすることが必要な場合があることでしょう。

- その日の Teams の使用が終わったため
- 別のアカウントを使用する必要がある
- 他のユーザーと共有しているデバイスを利用しているため

このような理由などから、Teams ではアプリからサインアウトし、セッションを終了することができます。

## <a name="account-sharing-between-apps"></a>アプリ間のアカウント共有

最新のオペレーティング システムでは、デバイス上のさまざまなアプリ間でアカウントを共有できます。 このシングル サインオン (SSO) 設計により、ユーザーは 1 つ 1 つのアプリにサインインすることなく、デバイス上で複数のアプリを使用することができます。 Teams はこの動作を制御しませんが、このデザインがエンド ユーザー エクスペリエンスに提供する利便性を利用します。

SSO はサインアウトに重要な影響を与えます。ユーザーが Teams からサインアウトすると、自分のアカウントに関連付けられているデータは Teams アプリから削除されますが、デバイス上の他のアプリは引き続き自分のアカウントにアクセスできます。 また、ユーザーが同じアカウントで Teams にもう一度サインインすることを選択した場合、資格情報の再入力を求められることがあります。

## <a name="sign-out-of-teams-on-desktop"></a>デスクトップ上の Teams からサインアウトする

Teams デスクトップ クライアントまたはブラウザーからサインアウトするには、アプリの上部にあるプロファイル画像を選択し、**[サインアウト]** を選択します。

デスクトップ アプリの場合は、タスク バーのアプリ アイコンを右クリックし、**[サインアウト]** を選択することもできます。

複数のアカウントを追加している場合は、個々のアカウントからサインアウトする必要があります。 Teams でアカウントからサインアウトしたら、アカウントにアクセスするために、アプリの次回の起動時に資格情報をもう一度入力する必要がある場合があります。

## <a name="sign-out-of-teams-on-mobile-devices"></a>モバイル デバイスで Teams からサインアウトする

モバイルでは、メニューに移動して [**その他**] メニューを選択し、[**サインアウト**] を選択することで、Teams からサインアウトできます。サインアウトすると、ユーザーは次にアプリを起動するときに、資格情報を再入力する必要があります。

### <a name="global-sign-in-and-sign-out-for-frontline-workers"></a>現場担当者向けのグローバル サインインとサインアウト

Teams Android アプリは、グローバルなサインインとサインアウトをサポートするようになり、現場担当者は手間なしでサインインとサインアウトができるようになりました。 従業員は、共有デバイス プールからデバイスを選択し 1 回サインインするだけで、シフト時間中は"自分用のデバイス" にすることができます。 これらのユーザーは、シフトの最後に、サインアウトすると、デバイスに対してグローバルにサイン アウトできます。 これにより、デバイスから個人情報と会社情報がすべて削除され、デバイスがデバイスプールに返されます。 この機能を利用するには、デバイスを shared モードにする必要があります。 共有デバイスをセットアップする方法の詳細については、「[Androidで共有デバイスモードを使用する方法](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode) 」を参照してください。

## <a name="manual-cleanup"></a>手動クリーンアップ

まれに、Teams がサインアウト時に完全にクリーンアップできなかった可能性があります。ユーザー レポートに基づく一般的な原因としては、システムで実行されているサービスによってファイルがロックされていることが含まれますが、個人のデバイス構成やポリシー、デバイスに適用されたユーザー アクセス許可によっては、別の理由も考えられます。

この問題の一般的な原因の 1 つは、Teams が既存のアカウントを自動的に選択して、ユーザーのサインインしようとすることです。 このような場合、ユーザーは Teams キャッシュを手動でクリーンアップしたいと思うかもしれません。 詳細については、「[サインインするか、Teams からアカウントを削除する](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)」を参照してください。

## <a name="related-topics"></a>関連トピック

[サインインするか、Teams からアカウントを削除する](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)