---
title: Skype for Business Server 2015 ストレスとパフォーマンス ツール
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
description: 2015 Skype for Business Serverおよびパフォーマンス ツールは、非実稼働環境またはテスト環境での容量計画とパフォーマンス調整中に使用されます。
ms.openlocfilehash: 1dff13905145752c57b02795e9aab07737d51b33d94d6355ce5f8c55fa62e7ea
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328022"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 ストレスとパフォーマンス ツール
 
2015 Skype for Business Serverおよびパフォーマンス ツールは、非実稼働環境またはテスト環境での容量計画とパフォーマンス調整中に使用されます。
  
2015 Skype for Business Serverおよびパフォーマンス ツールには、2015 年の容量計画を簡略化するツールSkype for Business Serverされています。 2015 Skype for Business Serverパフォーマンス ツールを使用すると、次の点に役立ちます。
  
- ハードウェアの計画を簡略化してSkype for Business Server
    
- パフォーマンス調整に関する知識とベスト プラクティスの向上
    
- 展開のパフォーマンスをSkype for Business Serverする
    
通常、このツールは[、Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md)計画ツールを使用してトポロジを設計し、Skype for Business Server [2015](../../management-tools/capacity-planning-calculator.md)容量計画計算機を使用してトポロジを絞り込む後に使用します。 

> [!NOTE]
> このツールは、2019 年Skype for Business Serverされません。
  
## <a name="tests"></a>テスト

ストレスとパフォーマンス ツールは、次の種類のユーザー負荷をシミュレートできます。
  
|||
|:-----|:-----|
|インスタント メッセージング (IM) とプレゼンス  <br/> |電話会議  <br/> |
|アプリケーション共有  <br/> |公衆交換電話網 (PTSN) シミュレーションを含むボイス オーバー IP (VoIP)  <br/> |
|Web Access クライアント会議  <br/> |会議自動応答  <br/> |
|応答グループ  <br/> |配布リストの展開  <br/> |
|アドレス帳のダウンロードとアドレス帳のクエリ  <br/> |拡張 911 (E911) 通話と場所プロファイル (ダイヤル プラン)  <br/> |
|MultiView  <br/> |データの共同作業  <br/> |
|モビリティ  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>2015 年 2015 年Skype for Business Serverパフォーマンス ツールに含まれるアプリケーションとファイル

これらのアプリケーションは、ストレスとパフォーマンス ツールSkype for Business Serverの一部です。
  
|**ツール**|**説明**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |このツールは、ユーザーと連絡先を作成するために使用されます。  <br/> |
|UserProfileGenerator.exe  <br/> |シミュレートするユーザー負荷の特性を構成するために使用します。  <br/> |
|LyncPerfTool.exe  <br/> |ユーザーの負荷をシミュレートするツール。  <br/> |
|Default.tmx  <br/> |2015 Skype for Business Serverツールを使用するために必要です。  <br/> |
|プロビジョニング スクリプトの例  <br/> |特定のシナリオに基づいてロード テストを実行するトポロジを構成するために使用します。 特定の環境に関連付けするために、それらを変更する必要がある可能性があります。  <br/> |
   
## <a name="topics-in-this-section"></a>このセクションのトピック

詳細を知る必要がある場合は、次の記事を確認する必要があります。
  
- [Busines Stress and Performance Tool Skypeの前提条件とセットアップ](prerequisites-and-setup.md)
    
- [2015 年Skype for Business Serverパフォーマンス ツールのパフォーマンス シナリオ](scenarios.md)
    
  - [ストレスとパフォーマンスのシナリオで負荷を実行するトポロジのプロビジョニング](provisioning-the-topology-to-run-load.md)
    
  - [2015 年 2015 年Skype for Business Serverパフォーマンス ツールのポリシーの構成](configuring-policies.md)
    
- [2015 Skype for Business Serverパフォーマンス ツールの使用](using-the-tool.md)
    
- [2015 年Skype for Business Serverパフォーマンス ツールに関する FAQ](faq.md)
    

