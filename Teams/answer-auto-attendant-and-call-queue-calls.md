---
title: 自動応答および呼び出しキューの通話に Teams から直接応答する
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: クラウドの自動応答とキューを呼び出すし、チームでこれらの呼び出しを回答する方法を説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: beb4b043798ba5348da1d460f49ff93e6aff55e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33900931"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>自動応答および呼び出しキューの通話に Teams から直接応答する
===========================================================

チームのユーザーでは、受信でき、クラウドの自動応答とそのチームのクライアントから直接呼び出しキューからの呼び出しに応答することができます。 チーム ユーザーの場合は、自動アテンダントの機能が、一般的に使用できる、および呼び出しキュー機能は、プレビューでは。 

## <a name="what-are-auto-attendants-and-call-queues"></a>自動応答とキューを呼び出すか。

自動応答をクラウドには、一連の音声プロンプトまたは組織に電話するときに、人間のオペレーターではなく相手に対して再生するオーディオ ファイルが用意されています。 自動応答により、発信者はメニュー システムを介して、通話、電話機のキーパッド (DTMF) を使用したユーザーの特定、音声認識を使用した音声入力を行うことができます。

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>自動アテンダントまたは呼び出しキューの呼び出しを処理します。

ユーザーは通話に応答する前に、自動アテンダントまたは呼び出しキューからの着信呼び出しを区別することになります。 名前や呼び出し元の数、および呼び出しのたびにした呼び出し元がアクセスしようと、呼び出し元に対応するため、内容をユーザーに与えるについての情報が含まれます。

ユーザーに、自動アテンダントまたは呼び出しキューからの着信呼び出しを表示する方法を次の図に示します。

![着信通知](media/answer-auto-attendant-and-call-queue-calls-image1.png)

ユーザーが、他の呼び出し & #x 2014; のような呼び出しを処理できる、自動アテンダントまたは呼び出しキューの呼び出しが応答すると、1 回追加することや会議の他のユーザーまたは別の関係者への呼び出しを転送します。 また、自動アテンダントの呼び出しは、ユーザーの構成に基づいて転送されます。

> [!NOTE] 
> ユーザーの構成に基づくキューの呼び出しの呼び出しは転送されません。 これは、呼び出し元は、エージェントが通話に応答するまでキューに残ることを確認するのには、呼び出し元が予期せずに転送されていないとします。

## <a name="supported-clients"></a>サポートされているクライアント

自動アテンダントおよび呼び出しキューの呼び出しのサポートは、次のクライアントで利用可能なです。

-   Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)
-   Microsoft Teams Mac クライアント
-   マイクロソフト チームの iPhone アプリ
-   マイクロソフト チーム Android アプリ

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>マイクロソフト チームの自動応答、および呼び出しキューのサポートを構成します。

自動応答を受信し、マイクロソフトのチームにキューの呼び出しを呼び出しには、相互運用性ポリシーを構成し、ポリシーをアップグレードする必要があります。 [移行とビジネス用の Skype とチームを使用する組織の相互運用性](migration-interop-guidance-for-teams-with-skype.md)を確認してください。 自動応答がない場合や呼び出しキューを構成したいと考えては、[クラウドの自動応答を設定](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)し、[クラウドの呼び出しキューを作成する](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)を参照してください。

## <a name="related-topics"></a>関連トピック

-   [Office 365 の電話システムとは](what-is-phone-system-in-office-365.md)
-   [クラウドの通話キューを作成する](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [クラウドの自動応答とは](what-are-phone-system-auto-attendants.md)
-   [クラウドの自動応答をセットアップする](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

