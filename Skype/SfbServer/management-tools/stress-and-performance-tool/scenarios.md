---
title: Skype for Business Server 2015 ストレスおよびパフォーマンスツールのパフォーマンスシナリオ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: パフォーマンスと負荷テストを実行するために、ストレスおよびパフォーマンスツールを使用して Skype for Business Server 2015 を構成するために必要なタスク。
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983852"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 ストレスおよびパフォーマンスツールのパフォーマンスシナリオ
 
パフォーマンスと負荷テストを実行するために、ストレスおよびパフォーマンスツールを使用して Skype for Business Server 2015 を構成するために必要なタスク。
  
Skype for business Server 2015 のストレスおよびパフォーマンスツール (LyncPerfTool) を実行するには、Skype for Business Server 2015 トポロジを、ユーザーに関連するシナリオに対して最初に構成する必要があります。 Skype for Business Server 2015 が構成されていない場合、または正しく構成されていない場合は、負荷シミュレーションが失敗する可能性が高くなります。 Skype for business Server 2015 のストレスおよびパフォーマンスツールを使用して、Skype for business Server 管理シェルスクリプトと基本的なリソースファイルを[ツールのダウンロード](https://www.microsoft.com/download/details.aspx?id=50367)の一部として提供しています。 これらは、Skype for Business Server の展開を構成するための開始点として使用できます。 この記事では、提供されている Windows PowerShell の例について説明します。
  
> [!NOTE]
> このトピックでは、Skype for Business Server 2015 の構成方法を説明するのに役立つ情報はありません。一般的に、そのための計画と展開に関するトピックがあります。 Skype for Business Server 2015 での Windows PowerShell の使用の詳細については、「挿入の概要」の「Skype for Business Server Management Shell」のドキュメントを参照してください。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Skype for Business Server 管理シェルスクリプトの実行について

ロードシミュレーションの準備に使用できるサンプル PowerShell スクリプトを提供しています。 これらのスクリプトは負荷シミュレーションを目的としているため、シンプルで寛容なものであることがわかります。 これは、運用環境には適していない場合があります。 これらのスクリプトはサンプルなので、これらを確認する必要があり、多くの場合、環境に関連する変更を行ってから、実際に使用できるようにする必要があります。 少なくとも、トポロジ (エージェントグループに割り当てられているエージェントを指定する場合) を考慮して、Response Service グループ (RSG) スクリプトを変更する必要があると考えられます。 しかし、必要でなければ、それを実行する必要はありません。
  
> [!CAUTION]
> これらのサンプルを確認し、理解してください。 スクリプトを実行すると、トポロジ内の既存の設定がすべて上書きされます。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>ストレスおよびパフォーマンスツールクライアントのバージョン名

以前に既定値の設定を変更したことがある場合は、クライアントバージョンチェックポリシーを構成する必要があります。 この点をよく理解していない場合は、[クライアントバージョンチェックのドキュメント](https://msdn.microsoft.com/vsto/jj923060)を確認してください。
  
ストレスおよびパフォーマンスツールでは、Skype for Business Server 2015 と通信するときに既定で次のユーザーエージェントバージョンが使用されます。
  
- LSPT/15.0.0.0 です (Skype for Business Server 2015 ストレスおよびパフォーマンスツール)
    
- OCPHONE/. 0.522
    
LyncPerfTool のモビリティ (UCWA) クライアントの場合:
  
- UCWA Perf ツール/Web 会議
    
- UCWA Perf ツール/モバイル
    

