---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Skype for Business Server 2015 応力とパフォーマンスツールは、非運用環境またはテスト環境でのキャパシティの計画とパフォーマンスのチューニングの際に使用されます。
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299517"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
Skype for Business Server 2015 応力とパフォーマンスツールは、非運用環境またはテスト環境でのキャパシティの計画とパフォーマンスのチューニングの際に使用されます。
  
Skype for Business Server 2015 のストレスとパフォーマンスのツールには、Skype for Business Server 2015 のキャパシティ計画を簡素化するためのツールが含まれています。 Skype for Business Server 2015 のストレスとパフォーマンスツールは、次のことを行うのに役立ちます。
  
- Skype for Business Server のハードウェア計画を簡素化する
    
- パフォーマンスのチューニングに関する知識とベストプラクティスの強化
    
- Skype for Business Server の展開のパフォーマンスを測定する
    
通常は、 [skype For Business server 2015 計画ツール](../../management-tools/planning-tool/planning-tool.md)を使用してトポロジを設計し、 [Skype for Business Server 2015 キャパシティプランニングの電卓](../../management-tools/capacity-planning-calculator.md)を使用してトポロジを絞り込みた後に、このツールを使用します。 

> [!NOTE]
> このツールは、Skype for Business Server 2019 では更新されません。
  
## <a name="tests"></a>テスト

ストレスとパフォーマンスのツールでは、次の種類のユーザーロードをシミュレートできます。
  
|||
|:-----|:-----|
|インスタントメッセージング (IM) とプレゼンス  <br/> |電話会議  <br/> |
|アプリケーション共有  <br/> |公衆交換電話網 (PTSN) シミュレーションなどのボイスオーバー IP (VoIP) シミュレーション  <br/> |
|Web Access クライアント会議  <br/> |会議の自動応答  <br/> |
|応答グループ  <br/> |配布リストの展開  <br/> |
|アドレス帳のダウンロードとアドレス帳のクエリ  <br/> |拡張 911 (E911) 通話と位置情報プロファイル (ダイヤルプラン)  <br/> |
|MultiView  <br/> |データの共同作業  <br/> |
|モビリティ  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 のストレスとパフォーマンスのツールに含まれているアプリケーションとファイル

これらのアプリケーションは、Skype for Business Server のストレスとパフォーマンスツールの一部です。
  
|**ツール**|**説明**|
|:-----|:-----|
|Userプロビジョニングツール .exe  <br/> |このツールは、ユーザーと連絡先を作成するために使用されます。  <br/> |
|UserProfileGenerator  <br/> |シミュレートしているユーザーロードの特性を構成するために使用されます。  <br/> |
|LyncPerfTool  <br/> |ユーザーロードをシミュレートするツール。  <br/> |
|Tmx  <br/> |Skype for Business Server 2015 Logging Tool を使用するために必要です。  <br/> |
|プロビジョニングスクリプトの例  <br/> |特定のシナリオに基づいて、ロードテストを実行するためのトポロジを構成するために使われます。 特定の環境に関連するように、これらを変更する必要があります。  <br/> |
   
## <a name="topics-in-this-section"></a>このセクションのトピック

詳細情報が必要な場合は、次の記事を参照してください。
  
- [Skype for Busines Stress and Performance Tool の前提条件と設定](prerequisites-and-setup.md)
    
- [Skype for Business Server 2015 ストレス/パフォーマンスツールのパフォーマンスシナリオ](scenarios.md)
    
  - [ストレスとパフォーマンスのシナリオでのロードを実行するためのトポロジのプロビジョニング](provisioning-the-topology-to-run-load.md)
    
  - [Skype for Business Server 2015 応力とパフォーマンスツールのポリシーを構成する](configuring-policies.md)
    
- [Skype for Business Server 2015 のストレスとパフォーマンスのツールを使用する](using-the-tool.md)
    
- [Skype for Business Server 2015 のストレスとパフォーマンスのツールについてよく寄せられる質問](faq.md)
    

