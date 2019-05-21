---
title: Skype for Business Server の容量計画計算ツール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: '概要: 容量計算機の使用方法'
ms.openlocfilehash: 24e268c6ecc3cc48fbfb4405f1e5e6b008639944
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274458"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business Server の容量計画計算ツール
 
**概要:** 容量計算機の使用方法

> [!NOTE]
> この記事では、Skype for Business Server 2015 ダウンロードについて説明しますが、以下に該当します。
> - Skype for Business Server 2019
> - Skype for Business Server 2015
  
Skype for [Business server 2015 キャパシティ電卓](https://www.microsoft.com/en-us/download/details.aspx?id=51196)と[Skype for Business Server 2019 キャパシティ電卓](https://www.microsoft.com/en-us/download/details.aspx?id=57509)は、Skype for business[計画ツール](https://www.microsoft.com/en-us/download/details.aspx?id=50357)と展開ドキュメント (skype for business[の計画) を強化しています。サーバー2015の展開](../plan-your-deployment/plan-your-deployment.md)と[プラン Skype For business Server 2019 の展開](../../SfBServer2019/plan/plan-your-deployment-2019.md)をそれぞれ計画しています。 この計算機は、ガイドをよくお読みになり、計画ツールを使って推奨のトポロジを作成後に使用してください。
  
Skype for Business Server キャパシティ電卓は、組織が使用しているユーザーの数と通信ツールに基づいてサーバー要件を決定するのに役立ちます。 ユーザー プロファイルとユーザーに対して有効にしたい機能が決定したら、この計算機を使って必要とするサーバー、メモリ、帯域幅数を決定します。 計算機のこのバージョンでは、ディスク I/O 要件に対するガイダンスは提供しません。
  
特定のユーザー プロファイルに関する正確な詳細情報があれば、計算機を最大限に活用できます。たとえば、音声対応ユーザーの割合、1 時間あたりの各ユーザーの平均通話数、通話時間、会議での同時ユーザーの割合によって、サーバー要件が大幅に変わる可能性があります。計算機によって作成される推奨事項の精度は、提供する情報の精度によって変わります。
  
計画ツールとキャパシティ計画電卓を使用したら、提案された計画済みのロードをシミュレートして、Skype for Business Server が適切にプロビジョニングされることを確認する必要があります。 シミュレートされたロードでストレステストを実行するには、Skype for business Server のストレスと[パフォーマンスツール](https://technet.microsoft.com/en-us/library/mt631400.aspx)で説明されている[Skype for Business server のストレスとパフォーマンスのツール](https://www.microsoft.com/en-us/download/details.aspx?id=50367)を使用します。
  
## <a name="using-the-capacity-calculator"></a>容量計算機の使用

計算機は Microsoft Excel のスプレッドシートです。 オレンジ色のセルが入力用です。 セルに既定値が入力されます (skype for business server 2015 8万、1つのプールの1つのプールに12個のフロントエンドサーバーがある場合、1つのプールに1つのプールがあり、1つのプールに16個 106000 2019 のフロントエンドサーバーがある場合)、これらの値を次のように変更する必要があります。組織のニーズに合わせてください。
  
使用モデルには次のセクションが含まれます。容量要件を計算するには、次のように、シートの上から下に行ごとに順番にデータを入力していきます。 
  
 **インスタント メッセージングとプレゼンス**
  
- [**ユーザー数**] に、同時にサインインできるユーザー数を入力します。 この数は通常はプロビジョニングされたユーザーの総数の 80% です。 ほとんどの場合、同時ユーザーの 100% で IM とプレゼンスが有効です。 既定値は、Skype for business Server 2015 用の8万、および Skype for Business Server 2019 の106000ユーザーです。
    
- [**連絡先リストの平均連絡先数**] は、システム要件の検証に使用している連絡先の数を示します。この数は固定で、変更できません。
    
  **エンタープライズ VoIP**
  
- [**Users enabled for Enterprise Voice (エンタープライズ VoIP が有効なユーザー)**] に、エンタープライズ VoIP が有効なユーザーの割合を入力します。既定値は 60% です。 
    
- [**Average number of calls per user per hour (peak) (1 時間あたりのユーザーごとの平均通話数 (ピーク時))**] に、負荷のピーク時に平均的なユーザーが参加すると思われる 1 時間あたりの通話数を入力します。既定値は 4 です。 
    
- [**Percentage of calls that use media bypass (メディア バイパスを使用する通話の割合)**] に、仲介サーバーをバイパスするユーザーによる発信の割合を入力します。既定値は 65% ですが、地理的に拡大するあるいは家から作業するユーザーのパーセンテージが大きい場合は、値を下げてもかまいません。
    
- [ **UC pstn 通話に参加している音声ユーザーの割合**] に、uc pstn 通話の組織の通話の割合を入力します。 既定値は 60% です。
    
- [**Percentage of voice users involved in UC-UC calls (UC-PSTN 通話に含まれる音声ユーザーの割合)**] は、UC-UC 通話のみが有効な、エンタープライズ VoIP 対応ユーザーの割合を示しています。この数値は、[**Percentage of voice users enabled for UC-PSTN calls (UC-PSTN 通話が有効な音声ユーザーの割合)**] の入力値に基づいて計算されます。 
    
  **会議**
  
- [**Percentage of users in concurrent conferences (同時会議のユーザーの割合)**] に、会議に同時参加するユーザーの割合を入力します。既定値は 5% です。 
    
- [**Percentage of conferences with group IM only (no voice) (グループ IM のみ (音声なし) の会議の割合)**] に、インスタント メッセージングのみを必要とし、音声を使用しない会議の割合を入力します。既定値は 10% です。
    
- [**Percentage of users using dial-in conferencing (ダイヤルイン会議を使用するユーザーの割合)**] に、ダイヤルイン会議を使用する会議への同時参加者の割合を入力します。既定値は 15% です。
    
- [**Percentage of conferences using voice (音声を使用する会議の割合)**] に、音声を使用しない会議の割合を入力します。 
    
  - 20% の音声会議に通常のビデオも含まれる場合は、[**Including video (no Multi View) (ビデオを含む (マルチビューなし))**] チェック ボックスをオンにします。
    
  - 20% の会議にマルチビュー ビデオも含まれる場合は、[**Including Multi View (マルチビューを含む)**] チェック ボックスをオンにします。
    
  - 音声会議の 50% にもアプリケーション共有が含まれている場合は、[**アプリケーション共有**を含める] チェックボックスをオンにします。
    
  - 20% の音声会議にデータのアップロード (PowerPoint のプレゼンテーションなど) が含まれる場合は、[**Including web conferencing (Web 会議を含む)**] チェック ボックスをオンにします。
    
  **モビリティ**
  
- [**モビリティに対応しているユーザーの割合**] に、モバイルデバイスを使用して Skype For business Server に接続できるユーザーのパーセンテージを入力します。 既定値は 40% です。 
    
必要な情報をすべて入力すると、容量計算機によって要件が見積られます。 黄色のセルには、Skype for Business Server パフォーマンスラボで実行されたテストに基づいた CPU、メモリ、帯域幅の要件の計算値が表示されます。 この数値はガイドラインとして提供されるもので、すべてのバリエーションを逐一テスト、検証したわけではありません。 次の値が計算されます。 
  
- [**フロントエンド CPU**]: 全体の負荷が、テストで使用されたサーバーと同じ仕様のフロントエンド サーバーによって処理された場合の CPU 使用率の割合です (詳細は、本記事の最後を参照)。
    
- [**ネットワーク (Mbps)**]: 対応するワークロードの帯域幅要件 (メガビット/秒 (Mbps) 単位) です。
    
- [**メモリ (GB)**]: 対応するワークロードで必要なメモリ (ギガバイト (GB) 単位) です。
    
緑色のセルには、入力した使用モデルの推奨事項が表示されます。 
  
- **フロントエンドサーバーの合計**: 必要な物理サーバーの数は、デュアルプロセッサ、16ビット、2260メガビット、2673 v3、または Skype For business server 2019 を搭載した Skype For business server 2015 を実行している専用サーバーに基づいています。プロセッサ、hex-core。
    
    ハイパースレッドを有効にすると、音声/ビデオをサポートするサーバーのパフォーマンスが上がることがわかっているのでお勧めします。
    
- [**エッジ サーバー**]: すべての同時ユーザーの 30% がエッジ サーバー経由で通信するという前提に基づいた、必要なエッジ サーバー数です。この割合を計算機で変更することはできません。 
    
- [**アーカイブ/通話詳細記録/ Quality of Experience (QoE) のサービス ストア**]: アーカイブ機能や監視機能に必要なストア数です (組織で有効な場合)。
    
- [**必要なバックエンド データベース サーバー (必要なプール)**]: 選択したワークロードのサポートに必要なバックエンド データベース サーバーの数です。
    
また、フロントエンド サーバーの合計の次の行には、計画したすべてのワークロードを組み合わせた場合の、サーバーとネットワークへの負荷に関する詳細情報が表示されます。
  
- [**CPU の平均負荷**]: フロントエンド サーバーあたりの平均 CPU 使用率です。
    
- [**ネットワーク (Mbps)**]: 入力した使用モデルのサポートに必要な帯域幅割り当てです。
    
- [**メモリ (GB)**]: 各フロントエンド サーバーで必要なメモリ (ギガバイト単位) です。
    
### <a name="adjusting-for-your-processors"></a>プロセッサに応じた調整

スプレッドシートの CPU 使用量の図では、すべての Skype for Business Server 2015 サーバーに、2.26 GHz、少なくとも 32 GB のメモリ、および 8 GB 以上の 1万 RPM ハードディスクドライブと、72 GB 以上の空きディスク領域があることを前提としています。 各 Skype for Business Server 2019 Server では、スプレッドシートの CPU 使用量について、各サーバーにはデュアルプロセッサ、Intel Xeon E5-2673 v3、64 GB 以上のメモリ、8以上の 1万 RPM ハードディスクドライブ (少なくとも 72 GB の空きディスク) があることを前提としています。スピード.
  
サーバーにこの仕様とは異なるプロセッサが搭載されている場合は、数値を調整してご使用のハードウェアに合わせることができます。
  
