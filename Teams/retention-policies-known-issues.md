---
title: マイクロソフトのチームでの保存ポリシーの既知の問題
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: マイクロソフトのチーム ・ リテンション ・ ポリシーの既知の問題の現在のリストです。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b6d71a1b2422dfadfbc7ae0fb87e607fd288152
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004587"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>マイクロソフトのチームでの保存ポリシーの既知の問題

次既知の問題をされているチームのリテンション ・ ポリシーの追跡し、調査します。

- 選択チームのチャネル メッセージの場所の行で、チームでもないチームには、Office 365 のグループを参照してください可能性があります。 これは、将来的に解決されます。

- チームのチャットの場所の行で [ユーザーの選択] の下、来園者とユーザーのメールボックスではないを表示ことがあります。 リテンション ・ ポリシーを来園者を設定する必要はないし、これらの一覧から削除することに努めています。

- Exchange のライフ サイクルのアシスタント (ELC) は毎日実行されるが、7 日間の SLA。 結果として、60 日より古いアイテムを削除するのには、チームの保持ポリシーがあれば、これらの項目でした永続化を 67 日間のことができます。 新しい状況ではありません - 交換モデルに依存しています。 もちろん、ほとんどの場合、時間はかかりません。


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |判断ポイント         |組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?         |
|![次のステップ アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |次のステップ         |必要なセキュリティとコンプライアンスの機能を文書化します。         |
