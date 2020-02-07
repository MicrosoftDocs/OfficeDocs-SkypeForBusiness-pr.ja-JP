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
description: 導入計画のフェーズ2の主要な決定を行う
f1.keywords:
- CSH
ms.custom: Adopt
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1dfd82cc10f90616dcdd557e9d1d70f36a9ae1f
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837817"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Microsoft Teams のガバナンスのクイック スタート

次のアクティビティは、同時に行われ、主要なチームのすべてまたは一部を対象としている可能性があります。 ベストプラクティスとして、Teams を使用して最初の実験を完了した後の、大規模なガバナンスとセキュリティの会話を延期してください。 これにより、その後の日付に対する決定が簡略化されます。 このフェーズでは、いくつかの決定を行う必要があります。 問題を解決するには、最初に次の質問に答える必要があります。

- この限定勤務のオンボードに参加するのに適した候補として、以前の評価からのステークホルダーはどれですか?
- このフェーズの候補として適切なユースケースを提案します。  
- 組織内の従業員が事前に採用して、有意義で定期的なフィードバックを提供している場合は、十分な関心がありますか? 

詳細については、「 [teams のガバナンスの計画](plan-teams-governance.md)」を参照して、 [teams でのライフサイクル管理を計画](plan-teams-lifecycle.md)してください。

## <a name="an-icon-representing-a-decision-pointmediateams-adoption-decision-iconpngdecisions"></a>![判断ポイントを表すアイコン](media/teams-adoption-decision-icon.png)行う

次の決定を行います (この時点では、これらの決定はフェーズ2にのみ適用されます)。

### <a name="decision-1-who-can-create-teams"></a>決定 1: チームを作成できるユーザー 

このフェーズを目的として、チームを作成できるユーザーを、コアプロジェクトチームに加えて早い導入者の人口に制限することができます。 これにより、必要に応じて追加のチームを作成することができます。 この動作を監視することで、広範な展開に関する重要な情報を得ることができます。

### <a name="decision-2-teams-naming-conventions"></a>判断 2: チームの名前付け規則 

チームの広範な展開のための名前付け規則を実装し、重複する名前を確認することをお勧めします。 フェーズ2では、初期プロジェクトでのみ手動の名前付け規則を実装することをお勧めします。 このためのベストプラクティスは、早期導入プロジェクトチームと共に対話型のオンボードを実施し、自分の名前を選択できるようにすることです。 これにより、従業員が作業についてどのように考えているかを把握することができます。また、後で大規模な名前付け規則を作成することが重要になります。 (対話型オンボードの要素に関する追加情報は、このガイドの後半で説明します)。

### <a name="decision-3-guest-access"></a>決定 3: ゲストアクセス

お客様のプロジェクトの範囲と種類、および業界の性質によっては、パートナーやベンダーとのセキュリティで保護されたコラボレーションを実現することが、テストすることが必要な機能である場合があります。 適切なテナントコントロールを使用して、チームの実装にゲストを追加できるユーザーを制限することができます。 

### <a name="decision-4-approved-apps"></a>決定 4: 承認されたアプリ

Teams の最適な使用方法には、他のアプリとエクスペリエンスとの統合が含まれます。 少なくとも、チームのエクスペリエンスで最初のパーティとおすすめのアプリを有効にする必要があります。 組織で使用されているユースケースやその他のアプリによっては、追加のアプリをコントロール実験の一部として含めることを選択できます。 

### <a name="decision-5-are-meetings-included-in-your-test"></a>判断 5: 会議はテストに含まれていますか。 

Teams の会議エクスペリエンスは高品質で、ビデオチャットをサポートしており、従業員がより効率的に共同作業を行うことができます。 技術チームに相談して、簡単な VoIP 会議を含めることができるようにします。 電話会議またはボイスサービスの有効化は、通常、実験のこのフェーズから除外されます。ただし、お客様のコアプロジェクトチーム、お客様のテクニカルレディネス、および組織内の他のボイス/会議サービスの状態によって異なります。 チームの実装からより多くの価値を得るために、ビデオチャットや VoIP 会議を実験に含めることをお勧めします。 

### <a name="decision-6--data-security"></a>判断 6: データのセキュリティ

幅広い展開の準備として、環境内のチームの種類を分類するためにセキュリティラベルを使用することを選択できます。 この実験を目的として、 [teams でガバナンスを計画](plan-teams-governance.md)することをお勧めします。また、Office 365 組織の Teams データに基本的なアイテム保持ポリシーが設定されていることを確認することをお勧めします。 この作業を完了するには、Office 365 管理者の権限が必要であるため、テクニカルチームとの協力が必要になることがあります。

### <a name="decision-7-length-of-your-experiment"></a>決定 7: 実験の長さ

チームの実装が成功すると、適切な勢い、焦点、高い知識が確実になります。 このフェーズの期間は60日間であり、早期導入が十分なビジネスサイクルを完了していることを確認することをお勧めします。 実験を延長すると時間がかかりすぎると、変更プログラムが失敗するリスクが増加します。ただし、この時間は組織ごとに異なります。  

![次の手順](media/teams-adoption-next-icon.png)を示すアイコン:[使用シナリオの定義](teams-adoption-define-usage-scenarios.md)
