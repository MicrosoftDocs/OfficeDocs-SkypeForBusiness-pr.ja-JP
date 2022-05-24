---
title: 記録と文字起こしのための会議ポリシーを管理する
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: 記録と文字起こしのTeamsで会議ポリシー設定を管理する方法について説明します。
ms.openlocfilehash: da7a5d43231abcb00339f2ffc2c57c7e90ff2d2e
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646366"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>&文字起こしを記録するための会議ポリシー設定

この記事では、次のような記録と文字起こしに固有の会議ポリシー設定について説明します。

- [文字起こしを許可する](#allow-transcription)
- [クラウド記録を許可する](#allow-cloud-recording)
- [国または地域以外のMicrosoft Store記録](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>文字起こしを許可する

これは、開催者単位とユーザーごとのポリシーの組み合わせです。 この設定は、会議の記録の再生中にキャプションと文字起こし機能を使用できるかどうかを制御します。 記録を開始したユーザーは、これらの機能で記録を操作できるようにするため、この設定を有効にする必要があります。

この設定をオンにすると、会議記録に保存されているトランスクリプトのコピーが作成されます。これにより、会議記録で **検索**、**CC**、および **トランスクリプト** を実行できるようになります。

記録された会議の文字起こしは、現在、Teams会議で自分の言語を設定または英語を話すユーザーに対してのみサポートされています。

## <a name="allow-cloud-recording"></a>クラウド記録を許可する

この設定は、開催者ごとのポリシーとユーザーごとのポリシーの組み合わせであり、会議を記録できるかどうかを制御します。 参加者のポリシー設定が有効になっており、同じ組織の認証済みユーザーである場合、会議の開催者または別の会議参加者が記録を開始できます。

フェデレーション ユーザーや匿名ユーザーなど、組織外のユーザーは記録を開始できません。 ゲスト ユーザーは記録を開始または停止できません。

![記録オプションが表示されたスクリーンショット](media/meeting-policies-recording.png)

次の例を見てみましょう。

|ユーザー |会議ポリシー  |クラウド記録を許可する |
|---------|---------|---------|
|Daniela | グローバル   | オフ |
|Amanda | Location1MeetingPolicy | オン|
|John (外部ユーザー) | 該当なし | 該当なし|

- Daniela によって開催された会議は記録できません。
- Amanda は Daniela によって開催された会議を記録できません。
- Amanda によって開催された会議を記録できます。
- Daniela は、Amanda によって開催された会議を記録できません。
- John は、Amanda によって開催された会議を記録できません。

クラウド会議の記録の詳細については、「[Teams のクラウド会議の記録](cloud-recording.md)」を参照してください。

## <a name="store-recordings-outside-of-your-country-or-region"></a>国または地域以外のMicrosoft Store記録

このポリシーは、会議レコードを別の国または地域に永続的に保存できるかどうかを制御します。 有効になっている場合は、記録を移行できません。 クラウド会議とレコーディングの保存場所の詳細については、「[クラウド会議の記録Teams](cloud-recording.md)参照してください。

## <a name="related-topics"></a>関連項目

- [Teamsのユーザーにポリシーを割り当てる](policy-assignment-overview.md)
- [クラウド会議の記録](cloud-recording.md)
