---
title: EDU 向けの Microsoft Teams 低帯域幅ガイダンス
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: EDU 向けの Microsoft Teams の記事は、低帯域幅に関連する会議やビデオの問題を解決するのに役立ちます。 親、教師、IT 管理者のいずれであっても、Teams のエクスペリエンスを向上できるオプションがあります。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: b254bfb89a96efed65e2c1fdba1c345825d81dc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111083"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>EDU 向けの Teams の低帯域幅状況を解決するためのヘルプ

Microsoft Teams で作業する際にパフォーマンスに影響を与える可能性のあるネットワーク要素は多数あります。低帯域幅は、制御が難しいと感じる要素の 1 つです。 次の状況について検討しましょう。

- 学校の低速インターネット接続。
- 1 人以上の学生の低速インターネット接続。
- 特定場所におけるネットワーク使用量が原因で低帯域幅になる一日の回数。
- 学校または学生のどちらに対してでもないローカルの停止が原因で生じ、パフォーマンスに影響を与える低帯域幅期間。
- 低帯域幅の問題であるかのように見える帯域幅以外の問題 (ハードウェアの問題など)。

この記事では、低帯域幅の問題が発生した場合に、さまざまな Times アクティビティに応じて実行するベスト プラクティスについて説明します。

> [!IMPORTANT]
> こちらの「[Microsoft Teams のメモリ使用方法](teams-memory-usage-perf.md)」の情報もご覧ください。低帯域幅の問題以外に、デバイスのリソースに問題が生じている場合もあります。 Microsoft Teams のネットワーク ガイダンスについては、「[Microsoft Teams 用に組織のネットワークを準備する](prepare-network.md)」をご確認ください。

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a>IT 管理者として低帯域幅の問題を解決する

IT 管理者として銘記しておくべき重要な点として、広範におよぶ低帯域幅の問題を迅速に解決できる解決策があっても、問題によっては教師または学生/親のレベルにおいてでさえもより狭い範囲に注目して解決できる場合があるので、慎重に考慮する必要があります。

つまり、大勢の学生たちに関して低帯域幅の問題が生じている場合には IT 管理者として対処するのが適切ですし、学生/教師レベルで対処しても有効でない場合にも適切であると言えます。

> [!NOTE]
> 時間があるときに、「[QoE のレビュー ガイド](quality-of-experience-review-guide.md)」を読むと役立ちます (EDU 特有の情報ではありませんが、有用です)。 参照すると、経験豊富な IT 管理者は、教師と学生のエクスペリエンスの詳細を把握できます。

### <a name="meetings-and-video"></a>会議とビデオ

低帯域幅の問題に関してまず注意を向ける必要があるのは、会議、特に会議のビデオです。 教育機関向けの設定で最適な会議エクスペリエンスにする点で、学生または教師によって報告される問題を扱うときに IT 管理者が考慮すべきアクションの一部を以下に取り上げます。

#### <a name="meeting-policies"></a>会議ポリシー

会議に関して低帯域幅の状況で最も注意を向けるべき領域の 1 つはビデオに関連する事柄です。 幸いなことに Teams は検出された帯域幅を自動的に拡大縮小できるので、IT 管理者は開催者またはユーザーのレベルで、あるいはその両方のレベルでポリシー オプションを設定し、ユーザーが指定の時間に作業に使用する必要がある帯域幅で最適なエクスペリエンスを得られるようにすることが可能です。

ポリシーで設定できる機能には、次のようなものがあります。

- ビデオを完全に無効にして、だれも有効にできないようにします。
- メディア ビット レート (ユーザー単位で設定されます)。

オプションの詳細、および会議とビデオに設定する必要があるポリシーの詳細については、「[会議ポリシーの設定 - オーディオとビデオ](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video)」でご確認ください。

#### <a name="screen-sharing-policies"></a>画面共有ポリシー

別の例では、教師が取り上げている学習内容に関連するアプリケーションにのみ共有を限定する必要があるにもかかわらず、学生に自分の画面全体を共有している場合があります。 この点は、教師が個別に選択するよりも適している場合には、ポリシーで設定できます。

ポリシー設定を使用して画面共有を制限するうえで実行できる優れたアイデアについては、「[会議ポリシーの設定 - 画面共有](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video)」をご確認ください。

#### <a name="dial-in-number-for-meetings"></a>会議用のダイヤルイン番号

一部の学生にとっては、教室セッションにダイヤルインするほうが簡単な場合があります。 Teams 会議用のダイヤルイン番号を提供し、問題が生じている学生がビデオ会議に参加する代わりに電話をかけられるようにできます。

この点の詳細については、「[Microsoft Teams で招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照できます。

## <a name="low-bandwidth-scenarios-as-an-educator"></a>教師としての低帯域幅のシナリオ

教師には、低帯域幅の問題を解決するための手順を実行する権限が与えられている必要があり、以下のような状況では IT 管理によるアクションが優れた選択となることがあります。

- 問題が間欠的または一時的に発生する場合。
- 問題が生じるのが一日の特定の時刻であると予期できる場合や、低帯域幅の期間が予測可能である場合。

このような場合は、何らかの措置を講じることができます。

詳細については、「[帯域幅が少なくなったときに学業に Teams を使用する](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)」を参照してください。

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>親または学生としての低帯域幅のシナリオ

帯域幅の問題が学生側にある可能性があり、教師と積極的に話し合う必要がある状況も存在します (たとえば、多数の学生が問題なくビデオ授業を視聴できるものの、少数の学生は困難であるという状況などです)。

多くの親にとってこうした問題のトラブルシューティングを行えると期待するのは実際的ではなく、低帯域幅の問題は、学生や親の制御下にないという可能性もあります (自宅が高帯域幅にアクセスできない、大勢のユーザーが近くにいて帯域幅を消費しているため実行できる事柄が制限される、インターネットが不安定になっているなどの状況が生じ得ます)。

親と学生向けに「[帯域幅が少なくなったときに学業に Teams を使用する](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)」の記事でガイダンスを提供しています。何らかの問題が生じている場合には、このガイダンスを確認し、推奨内容を試してください。