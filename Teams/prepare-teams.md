---
title: Microsoft Teams の導入に向けて現在の Skype for Business 環境を最適化する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Skype for Business から Microsoft Teams への移行を開始するためのガイダンス
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a9c9d4ccdbe3f3f1a2107c832b5437860e17d73
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
<a name="optimize-your-current-skype-for-business-environment-for-microsoft-teams"></a>Microsoft Teams の導入に向けて現在の Skype for Business 環境を最適化する
==============================================================

変更を実現するには時間がかかります。 組織は、展開ライフサイクル、リソース計画、技術的な準備状況、変更管理を考慮しなければなりません。 Microsoft は、Microsoft Teams がお客様の長期的な成功の実現に合致するよう最大限の取り組みを行っています。 弊社がこうした取り組みに注力する一方で、お客様は Teams の実装に向けた次のような準備を今すぐ開始することができます。 このガイダンスを完了することで、組織内での Teams の実装を成功に導くことができます。

## <a name="environmental-readiness"></a>環境の準備


以下のガイダンスを使用して、Teams の実装が確実に正常に完了するようにします。 このガイダンスは、Teams の展開の準備に向け、現在の Skype for Business 環境を検証する場合に役立ちます。   


### <a name="network-readiness-assessment"></a>ネットワークの準備状況の評価


Teams などのリアルタイム通信製品を実装する前に *Network Readiness Assessment (ネットワークの準備状況の評価)* を実施する必要があります。 *Network Readiness Assessment (ネットワークの準備状況の評価)* では、ネットワーク パフォーマンス、ネットワーク計画、開く必要のあるポートやプロトコルといったその他の一般的なネットワーキング要素に焦点が当てられます。 Skype for Business などのリアルタイム通信製品を既に使用している場合でも、*Network Readiness Assessment (ネットワークの準備状況の評価)* を実施することでネットワークの準備状況を把握することができます。

「[Network Readiness Assessment (ネットワークの準備状況の評価)](https://go.microsoft.com/fwlink/?linkid=859069)」ガイドを入手してください。

### <a name="my-advisor"></a>My Advisor


導入行程全体を通して、[My Advisor](http://aka.ms/myadvisor) の実践的なガイダンスを利用することをお勧めします。 My Advisor は、運用の成功に欠かせない Teams と Skype for Business Online の計画と管理で利用できる包括的なセルフサービス ガイドおよびツールセットです。


### <a name="quality-assessment"></a>品質評価


ユーザーを Teams の使用に関与させる前に、現在の Skype for Business の展開がリアルタイム メディアとしての品質基準を満たしているかどうかを確認する必要があります。 通話品質ダッシュボード (CQD) を使用して、使用量の監視や品質傾向の特定を行い、通話分析を使用してトラブルシューティングや個々の通話の品質インジケータの確認を行います。

通話品質ダッシュボードを使用してメディア品質を調査する方法については、「[CQD videos (CQD ビデオ)](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)」をご覧ください。

分析機能の呼び出しに関する詳細については、[ビジネス分析の電話の Skype](/SkypeForBusiness/using-call-quality-in-your-organization/set-up-call-analytics?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照してください。

### <a name="quality-champion-role"></a>品質チャンピオンの役割


組織は、品質チャンピオンの役割を担うユーザーまたはグループを特定する必要があります。 品質チャンピオンは、使用量に照らし合わせて品質メトリックスを確認し、品質の傾向や向上が必要な領域を特定します。

品質チャンピオンは通話品質に関連する問題が発生したときに頼りになる存在です。また、現在の使用量や品質傾向を確認し、実施項目を特定することで品質の問題を識別する領域の専門家 (SME) としての役割を持ちます。 品質チャンピオンは対応チームと協力して修復アクションを促し、その進捗状況や未解決案件を運営委員会に報告します。 通常、品質チャンピオンに最適な候補はカスタマー サービスの所有者です。 組織の規模や複雑さによっては、ユーザー エクスペリエンスに対して情熱を持ち、動向を特定する能力のあるユーザーならば誰でも品質チャンピオンとしての役割を担うことができます。この場合、品質チャンピオンは、修復を促すため、他のチームの協力を可能にする適切なスポンサーシップによってサポートされます。

品質チャンピオンの概念と品質レビューのツールや手法については、「[Manage a quality and reliable service delivery workshop (高品質および高信頼のサービスを提供するためのワークショップを管理する)](https://go.microsoft.com/fwlink/?linkid=859071)」をご覧ください。

## <a name="environmental-dependencies"></a>環境の依存関係


Teams は、複数の Office 365 サービスの組み合わせを使用するため、これらのサービスの適切な実装と運用に依存します。 該当するサービスには、SharePoint Online、Exchange Online、OneDrive for Business が含まれます。ただし、それらに限定されません。

これらのサービスは、すべてが必要なわけではありませんが、実装することを強くお勧めします。 実装しないサービスがあると、Teams が組織に提供できる機能に影響が及びます。 たとえば、SharePoint Online を実装する必要はありませんが、Teams はグループでのファイル共有などの特定の機能で SharePoint Online に依存します。 SharePoint Online を実装しないと、クライアントを介して提供される機能に影響が及びます。

要件の詳細については、次の記事をご覧ください。
- [Office 365 グループと Microsoft Teams](Office-365-groups.md)
- [Microsoft Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md) 
- [Exchange と Teams の連携](Exchange-Teams-interact.md)



