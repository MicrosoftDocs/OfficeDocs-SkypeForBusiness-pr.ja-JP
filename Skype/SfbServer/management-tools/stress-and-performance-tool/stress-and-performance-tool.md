---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Skype for Business Server 2015 Stress and Performance Tool は、非稼働環境またはテスト環境での容量計画とパフォーマンスチューニングの間に使用されます。
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814927"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
Skype for Business Server 2015 Stress and Performance Tool は、非稼働環境またはテスト環境での容量計画とパフォーマンスチューニングの際に使用されます。
  
Skype for Business Server 2015 Stress and Performance Tool には、Skype for Business Server 2015 の容量計画を簡素化するツールが含まれています。 Skype for Business Server 2015 Stress and Performance Tool は、次の場合に役立ちます。
  
- Skype for Business Server のハードウェア計画を簡素化する
    
- パフォーマンスのチューニングに関する知識とベスト プラクティスを向上させる
    
- Skype for Business Server 展開のパフォーマンスを測定する
    
このツールは、通常 [、Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) を使用してトポロジを設計し [、Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md)を使用してトポロジを絞り込む場合に使用します。 

> [!NOTE]
> このツールは、Skype for Business Server 2019 では更新されません。
  
## <a name="tests"></a>テスト

Stress and Performance Tool は、次の種類のユーザー負荷をシミュレートできます。
  
|||
|:-----|:-----|
|インスタント メッセージング (IM) とプレゼンス  <br/> |電話会議  <br/> |
|アプリケーション共有  <br/> |公衆交換電話網 (PTSN) シミュレーションを含むボイス オーバー IP (VoIP)  <br/> |
|Web Access クライアント会議  <br/> |会議自動応答  <br/> |
|応答グループ  <br/> |配布リストの展開  <br/> |
|アドレス帳のダウンロードとアドレス帳のクエリ  <br/> |拡張 911 (E911) 通話と場所プロファイル (ダイヤル プラン)  <br/> |
|MultiView  <br/> |データ コラボレーション  <br/> |
|モビリティ  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool に含まれるアプリケーションとファイル

これらのアプリケーションは、Skype for Business Server Stress and Performance Tool の一部です。
  
|**ツール**|**説明**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |このツールは、ユーザーと連絡先を作成するために使用されます。  <br/> |
|UserProfileGenerator.exe  <br/> |シミュレートするユーザー負荷の特性を構成するために使用します。  <br/> |
|LyncPerfTool.exe  <br/> |ユーザーの負荷をシミュレートするツール。  <br/> |
|Default.tmx  <br/> |Skype for Business Server 2015 ログ ツールを使用するために必要です。  <br/> |
|プロビジョニング スクリプトの例  <br/> |特定のシナリオに基づいて負荷テストを実行するトポロジを構成するために使用します。 特定の環境に関連付けられているものに変更する必要がある可能性があります。  <br/> |
   
## <a name="topics-in-this-section"></a>このセクションのトピック

詳細を知る必要がある場合は、次の記事を確認する必要があります。
  
- [Skype for Busines Stress and Performance Tool の前提条件とセットアップ](prerequisites-and-setup.md)
    
- [Skype for Business Server 2015 Stress and Performance Tool のパフォーマンス シナリオ](scenarios.md)
    
  - [ストレスとパフォーマンスのシナリオで負荷を実行するトポロジのプロビジョニング](provisioning-the-topology-to-run-load.md)
    
  - [Skype for Business Server 2015 Stress and Performance Tool のポリシーの構成](configuring-policies.md)
    
- [Skype for Business Server 2015 Stress and Performance Tool の使用](using-the-tool.md)
    
- [Skype for Business Server 2015 Stress and Performance Tool の FAQ](faq.md)
    

