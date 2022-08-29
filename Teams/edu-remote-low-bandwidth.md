---
title: Teams の低帯域幅シナリオのトラブルシューティング
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Teams の低帯域幅の問題に関連する会議やビデオの問題に関するヘルプを表示します。 親、教育者、IT 管理のいずれであっても、Teams のエクスペリエンスを向上させるためのオプションがあります。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f60095f20d62ed14b19d7c23493553efc39b872
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426814"
---
# <a name="troubleshoot-low-bandwidth-scenarios-for-teams"></a>Teams の低帯域幅シナリオのトラブルシューティング

この記事では、TEAMS で低帯域幅の問題に対処する場合のベスト プラクティスを IT 管理者に提供します。

Microsoft Teams を使用する場合、多数のネットワーク要素がパフォーマンスに影響を与える可能性があります。

- 学校の低速インターネット接続。
- 1 人以上の学生向けの低速インターネット接続。
- 1 日のうち、領域内におけるネットワーク使用量が原因で低帯域幅になる時間帯。
- 停止は学校や学生に対してローカルではなく、パフォーマンスに影響します。
- 低帯域幅の問題を引き起こすハードウェアに関する問題。

> [!IMPORTANT]
> [Microsoft Teams が](teams-memory-usage-perf.md)デバイスのリソース制限にメモリを使用する方法に関する記事を参照してください。
>
>Teams ネットワーク ガイダンスについては、「 [Microsoft Teams 用に組織のネットワークを準備する」を参照してください](prepare-network.md)。

## <a name="resolving-low-bandwidth-issues-for-it-admins"></a>IT 管理者の低帯域幅の問題を解決する

一部の問題は、個々のユーザー レベルの狭いフォーカスでのみ解決される場合があります。

帯域幅の問題が多くのユーザーに発生した場合、またはユーザー レベルで実行されたアクションが役に立たない場合は、学校全体のアクションが次の手順です。

> [!NOTE]
> また、「 [Quality of Experience Review Guide](quality-of-experience-review-guide.md)」を読むこともできます。 EDU 固有ではありませんが、貴重な情報があります。

### <a name="meetings-and-video"></a>会議とビデオ

低ネットワーク帯域幅に関連する会議の問題に対処する場合は、次のアクションを検討してください。

#### <a name="meeting-video-policies"></a>会議ビデオ ポリシー

Teams は、会議の品質をユーザーが検出した帯域幅に自動的にスケーリングします。 ただし、帯域幅を保持するためにさらに制限を設定できます。

ポリシーを使用して設定できる制限には、次のものがあります。

- ビデオを完全にオフにして、誰もビデオを使用できないようにします。
- ユーザーごとに設定されるメディア ビット レートを制限する。

会議とビデオに設定する必要があるその他のポリシーについては、「 [Teams の会議ポリシー設定: オーディオとビデオ](meeting-policies-audio-and-video.md)」を参照してください。

#### <a name="screen-sharing-policies"></a>画面共有ポリシー

Teams では、ユーザーは画面全体または個々のウィンドウを共有できます。

画面全体を共有する場合、ウィンドウを共有するよりも多くの帯域幅が使用されます。

- ポリシーを使用して、ユーザーが画面全体を共有できないように制限します。
- 画面全体ではなく、アプリケーションのみを共有するように教育者に指示します。

画面共有ポリシーについては、「 [Teams の会議ポリシー設定: オーディオとビデオ](meeting-policies-audio-and-video.md)」を参照してください。

#### <a name="dial-in-number-for-meetings"></a>会議用のダイヤルイン番号

一部の学生は、クラスルーム セッションにダイヤルインする方が簡単な場合があります。

- ビデオ会議に出席する代わりに、Teams 会議のダイヤルイン番号を入力します。

詳細については、「 [Microsoft Teams の招待に含まれる電話番号を設定する」を参照してください](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="low-bandwidth-scenarios-as-an-educator"></a>教師としての低帯域幅のシナリオ

次の状況では、教育者に帯域幅の問題のトラブルシューティングを行う方が、IT アクションよりも優れている可能性があります。

- 問題は断続的です。
- 問題が発生すると予測できる特定の時刻があります。

帯域幅の問題を解決するために教育者が実行できる手順については、「帯域幅 [が低い場合に学校の仕事に Teams を使用](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)する」を参照してください。

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>親または学生としての低帯域幅のシナリオ

帯域幅の問題が学生側にある場合があります。

- 自宅で高帯域幅にアクセスできない可能性があります。
- また、近くの領域に多くのユーザーが帯域幅を消費している可能性があります。
- インターネットが不安定になる可能性があります。

保護者と学生向 [けの帯域幅が低い記事の場合は、学校での作業に Teams を使用](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) する方法に関するガイダンスをまとめました。
