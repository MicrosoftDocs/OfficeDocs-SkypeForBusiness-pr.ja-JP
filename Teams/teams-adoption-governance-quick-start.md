---
title: Microsoft Teams のガバナンスのクイック スタート
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/29/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: 導入計画のフェーズ 2 の主な意思決定を行う
ms.custom: Adopt
MS.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecf91ea9a06b3984b65954617fe5690658015e52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896333"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Microsoft Teams のガバナンスのクイック スタート

次のアクティビティは、同時に行われます。また、主要なチームのすべてまたは一部が関係する可能性があります。 ベスト プラクティスとして、Teams で初期の実験が完了した後に、の大規模なガバナンスとセキュリティの会話を保留します。 これにより、後日に行う決定が簡単になります。 このフェーズでは、いくつかの決定を行う必要があります。 これらを成功させるには、まず次の質問に答える必要があります。

- 以前の評価から、この限定されたビジネスのオンボードに参加するのに適している関係者は誰ですか?
- この個人 (または個人グループ) は、このフェーズに適したユース ケースを提案しましたか?  
- 彼らは、組織内の従業員から早期導入者になり、有意義で定期的なフィードバックを提供するのに十分な関心を持っていますか? 

## <a name="decision-point-iconmediateams-adoption-decision-iconpngdecisions"></a>![判断ポイント アイコン。](media/teams-adoption-decision-icon.png)決定事項

次の決定を行います (この時点で、これらの決定はフェーズ 2 にのみ適用されます)。

### <a name="decision-1-who-can-create-teams"></a>決定 1: チームを作成できるユーザー 

このフェーズの目的のために、チームを作成できるユーザーを、コア プロジェクト チームに加えて、早期導入者の母集団に制限することができます。 これにより、早期導入者が必要に応じて追加のチームを作成することができます。 この動作を監視することにより、幅広い展開に関する重要な情報を得ることができます。

### <a name="decision-2-teams-naming-conventions"></a>決定 2: チームの名前付け規則 

Teams の幅広い展開のために、名前付け規則を実装し、重複する名前がないか確認したいかもしれません。 フェーズ 2 では、最初のプロジェクトに対してのみ、手動の名前付け規則を実装することをお勧めします。 このためのベストプラクティスは、早期導入者のプロジェクトチームとの対話型オンボードを実施し、彼らが自分の名前を選択できるようにすることです。 これにより、従業員が自分の職場をどのように考えるかを分析でき、後でより大規模な名前付け規則を作成する際に重要になります。 (対話型オンボードの要素に関する追加情報は、このガイドの後半に表示されます。)

### <a name="decision-3-guest-access"></a>決定 3: ゲスト アクセス

プロジェクトの範囲と種類、および業界の性質によっては、パートナーやベンダーとの保護された共同作業の有効化は、テストしたい重要な機能となる場合があります。 適切なテナントの制御を使用して、ゲストを Teams の実装に追加できるユーザーを制限できます。 

### <a name="decision-4-approved-apps"></a>判断 4: 承認済みアプリ

Teams の最良の使用例には、他のアプリをエクスペリエンスに統合することが含まれます。 少なくとも、技術チームは、Teams のエクスペリエンスにおいて最初のパーティとおすすめのアプリを有効にする必要があります。 使用例や組織で使用されている他のアプリによっては、制御された実験の一環として、追加のアプリを含めることができます。 

### <a name="decision-5-are-meetings-included-in-your-test"></a>決定 5: 会議はテストに含まれていますか? 

Teams 会議のエクスペリエンスは高品質で、ビデオ通話をサポートし、従業員の共同作業の効率を向上します。 環境に簡単な VoIP 会議を含める準備ができているかどうかを、技術チームに問い合わせください。 通常、電話会議や音声サービスの有効化は、実験のこのフェーズから除外します。ただし、これは、組織のコア プロジェクト チーム、技術の準備状況、および組織内の他の音声/会議サービスの状態によります。 Teams の実装からより多くの価値を得るために、ビデオ通話や VoIP 会議を実験に含めることをお勧めします。 

### <a name="decision-6--data-security"></a>決定 6: データのセキュリティ

幅広い展開の準備として、セキュリティ ラベルを使用して、環境内のチームの種類を分類することができます。 この実験では、「[Teams でのガバナンスを計画する](plan-teams-governance.md)」を参照して、Office 365 組織内の Teams データに基本的なアイテム保持ポリシーが設定されていることを確認することをお勧めします。 この作業を完了するには、Office 365 の管理者の権限が必要なため、技術チームとの調整が必要になる場合があります。

### <a name="decision-7-length-of-your-experiment"></a>決定 7: 実験の長さ

Teamsの実装に成功すると、適切な勢い、フォーカス、学習を確保しながら正常なペースで進みます。 早期導入者が十分なビジネスサイクルを実現できるように、プロジェクトのこのフェーズを 60 日間にすることをお勧めします。 実験を長時間延長すると、変更プログラムが失敗するリスクが高まります。ただし、この時間は組織によって異なります。  

![次のステップ アイコン](media/teams-adoption-next-icon.png) 次へ: [使用例を定義する](teams-adoption-define-usage-scenarios.md)
