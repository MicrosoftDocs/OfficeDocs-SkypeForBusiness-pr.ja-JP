---
title: Skype for Business Server 2015 ストレス/パフォーマンスツールのパフォーマンスシナリオ
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
description: パフォーマンスと負荷のテストを実行するために Skype for Business Server 2015 を構成するために必要なタスクを、ストレスとパフォーマンスのツールを使って実行する必要があります。
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803877"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 ストレス/パフォーマンスツールのパフォーマンスシナリオ
 
パフォーマンスと負荷のテストを実行するために Skype for Business Server 2015 を構成するために必要なタスクを、ストレスとパフォーマンスのツールを使って実行する必要があります。
  
Skype for Business Server 2015 応力とパフォーマンスツール (LyncPerfTool) を実行するには、まず、Skype for Business Server 2015 トポロジを、関連するシナリオに合わせて構成する必要があります。 Skype for Business Server 2015 が構成されていない場合、または正しく構成されていない場合は、ロードシミュレーションが失敗する可能性が高くなります。 Skype for Business Server 2015 のストレスとパフォーマンスのツールを使用して、Skype for Business Server 管理シェルスクリプトと基本的なリソースファイルをツールの[ダウンロード](https://www.microsoft.com/download/details.aspx?id=50367)の一部として提供しています。 これらは、Skype for Business Server の展開を構成するための出発点として使用できます。 この記事では、提供されている Windows PowerShell の例について説明します。
  
> [!NOTE]
> このトピックでは、Skype for Business Server 2015 を構成する方法について説明していません。一般的に、その他の計画と展開のトピックがあります。 Skype for Business Server 2015 での Windows PowerShell の使用について詳しくは、「ここで概要を挿入する」の「Skype for Business Server 管理シェルのドキュメント」をご覧ください。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Skype for Business Server 管理シェルスクリプトの実行について

ロードシミュレーションの準備に使用できる PowerShell スクリプトのサンプルを提供しています。 これらのスクリプトは、読み込みシミュレーション用のものであるため、単純で寛容なものにすることができます。 これは、実稼働環境に適していない可能性があります。 ここでも、これらのスクリプトはサンプルであり、多くの場合、それらを確認する必要があります。また、多くの場合、環境に関連する変更を行ってから実際に使用できるようになります。 少なくとも、トポロジを念頭に置いて応答サービスグループ (RSG) スクリプトを変更する必要があることを前提としています (エージェントグループに割り当てられているエージェントを指定するため)。 ただし、必要でない場合は、これを実行する必要はありません。
  
> [!CAUTION]
> これらのサンプルを確認して理解してください。 スクリプトは、実行時にトポロジの既存の設定を上書きします。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>ストレスとパフォーマンスのツールクライアントのバージョン名

以前に設定を既定値から変更した場合は、クライアントのバージョンチェックポリシーの構成が必要になることがあります。 この点について不明な点がある場合は、[クライアントのバージョンチェックのドキュメント](https://msdn.microsoft.com/en-us/vsto/jj923060)を確認してください。
  
ストレスとパフォーマンスのツールでは、Skype for Business Server 2015 と通信するときに、既定で次のユーザーエージェントバージョンが使用されます。
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 応力とパフォーマンスツール)
    
- OCPHONE 電話/0.522
    
LyncPerfTool のモビリティ (UCWA) クライアントの場合:
  
- UCWA Perf ツール/Web 会議
    
- UCWA Perf ツール/モバイル
    

