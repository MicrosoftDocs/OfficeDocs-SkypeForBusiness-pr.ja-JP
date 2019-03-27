---
title: 自動応答および呼び出しキューの通話に Teams から直接応答する
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 電話システムの自動応答、通話キューとチーム内のこれらの呼び出しを得ることができる方法を説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91c0d1ae8034766759baa9b832cbefd399306fd2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875979"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>自動応答および呼び出しキューの通話に Teams から直接応答する
===========================================================

チームのユーザーが受け取ることができ、ビジネス オンラインの Skype からの応答の呼び出しが自動的に応答し、キューをそのチームのクライアントから直接呼び出します。 チーム ユーザーの場合は、自動アテンダントの機能が、一般的に使用できる、および呼び出しキュー機能は、プレビューでは。 

## <a name="what-are-auto-attendants-and-call-queues"></a>自動応答とキューを呼び出すか。

電話システムの自動応答は、一連の音声プロンプトまたは組織に電話するときに、人間のオペレーターではなく相手に対して再生するオーディオ ファイルを提供します。 自動応答により、発信者はメニュー システムを介して、通話、電話機のキーパッド (DTMF) を使用したユーザーの特定、音声認識を使用した音声入力を行うことができます。

電話システム キューには、保留中の呼び出しを自動的に配置する機能などを検索する人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントの機能の電話番号への呼び出し際に使用するあいさつ文が含まれています。呼び出しが保留中の音楽をリッスンしています。 組織の 1 つまたは複数の呼び出しキューを作成します。

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

自動応答を受信し、マイクロソフトのチームにキューの呼び出しを呼び出しには、相互運用性ポリシーを構成し、ポリシーをアップグレードする必要があります。 [移行とビジネス用の Skype とチームを使用する組織の相互運用性](migration-interop-guidance-for-teams-with-skype.md)を確認してください。 自動応答がない場合や呼び出しキューが構成され、これを行うには、[電話システムの自動応答を設定](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)し、[電話システムの呼び出しキューを作成する](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)を参照してください。

## <a name="related-topics"></a>関連項目

-   [Office 365 の電話システムとは](what-is-phone-system-in-office-365.md)
-   [電話システムの呼び出しキューを作成する](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [電話システムの自動応答とは](what-are-phone-system-auto-attendants.md)
-   [電話システムの自動応答をセットアップする](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

