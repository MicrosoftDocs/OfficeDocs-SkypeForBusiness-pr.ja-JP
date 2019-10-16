---
title: 自動応答および呼び出しキューの通話に Teams から直接応答する
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: クラウド自動応答と通話キューについて説明し、Teams でこれらの通話に応答する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a508aeb6c5e1359c9b3432834f2f0f3d141aea2d
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516797"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>自動応答および呼び出しキューの通話に Teams から直接応答する
===========================================================

Teams ユーザーは、クラウド自動応答からの通話の受信と応答を、チームクライアントから直接行うことができます。 Teams ユーザーの場合は、自動応答機能が通常利用可能になり、通話キュー機能がプレビューに表示されます。 

## <a name="what-are-auto-attendants-and-call-queues"></a>自動応答と通話キューとは何ですか?

クラウド自動応答は、ユーザーが組織にコールインしたときに、発信者が人間のオペレーターではなく、一連の音声プロンプトや音声ファイルを提供します。 自動応答により、発信者はメニュー システムを介して、通話、電話機のキーパッド (DTMF) を使用したユーザーの特定、音声認識を使用した音声入力を行うことができます。

クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>自動応答または通話キューの呼び出しを処理する

ユーザーは、通話に応答する前に、自動応答または通話キューからの着信通話を区別することができます。 呼び出し元の名前や番号と共に、発信者が発信しようとしている相手に関する情報が含まれているため、ユーザーは呼び出し元に対処するための適切なコンテキストを提供します。

次の図は、自動応答または通話キューからの着信がユーザーにどのように表示されるかを示しています。

![着信通話の通知のスクリーンショット](media/answer-auto-attendant-and-call-queue-calls-image1.png)

自動応答または通話キューの呼び出しに応答すると、ユーザーは他の通話と同様に通話を処理することができ &#x2014;、別のユーザーに追加したり会議を行ったり、通話を別の相手に転送したりできます。 また、自動応答の呼び出しは、ユーザーの設定に基づいて転送されます。

> [!NOTE] 
> 通話キューの呼び出しは、ユーザーの構成に基づいて転送されません。 これは、エージェントが呼び出しに応答し、呼び出し元が予期せず転送されるまで、呼び出し元がキューに残るようにするためです。

## <a name="supported-clients"></a>サポートされているクライアント

自動応答と通話キューの呼び出しのサポートは、次のクライアントで利用できます。

-   Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)
-   Microsoft Teams Mac クライアント
-   Microsoft Teams iPhone アプリ
-   Microsoft Teams Android アプリ

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Microsoft Teams の自動応答と通話キューのサポートを構成する

Microsoft Teams で自動応答と通話キューの通話を受信するには、相互運用性ポリシーとアップグレードポリシーを構成する必要があります。 [チームと Skype For business を併用している組織のために、移行と相互運用性](migration-interop-guidance-for-teams-with-skype.md)を確認してください。 自動応答やコールキューが構成されていない場合は、「[クラウドの自動応答を設定](create-a-phone-system-auto-attendant.md)して、[クラウドの通話キューを作成](create-a-phone-system-call-queue.md)する」を参照してください。

## <a name="related-topics"></a>関連トピック

-   [Office 365 の電話システムとは](what-is-phone-system-in-office-365.md)
-   [クラウドの通話キューを作成する](create-a-phone-system-call-queue.md)
-   [クラウドの自動応答とは](what-are-phone-system-auto-attendants.md)
-   [クラウドの自動応答をセットアップする](create-a-phone-system-auto-attendant.md)

