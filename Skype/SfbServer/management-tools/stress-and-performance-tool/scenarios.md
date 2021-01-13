---
title: Skype for Business Server 2015 Stress and Performance Tool のパフォーマンス シナリオ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Stress and Performance Tool を使用して、パフォーマンスと負荷テストを実行するために Skype for Business Server 2015 を構成するために必要なタスク。
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814707"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool のパフォーマンス シナリオ
 
Stress and Performance Tool を使用して、パフォーマンスと負荷テストを実行するために Skype for Business Server 2015 を構成するために必要なタスク。
  
Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool) を実行するには、まず Skype for Business Server 2015 トポロジを、関連するシナリオ用に構成する必要があります。 Skype for Business Server 2015 が構成されていないか、正しく構成されていない場合、負荷シミュレーションが失敗する可能性が非常に高い。 Skype for Business Server 2015 Stress and Performance Tool では、ツールダウンロードの一部として、Skype for Business Server 管理シェル スクリプトと基本的なリソース ファイルの例を [提供しています](https://www.microsoft.com/download/details.aspx?id=50367)。 これらは、Skype for Business Server 展開を構成するための開始点として使用できます。 この記事では、以下の例Windows PowerShell説明します。
  
> [!NOTE]
> このトピックは、Skype for Business Server 2015 を一般的に構成する方法については説明しません。その他の計画および展開に関するトピックがあります。 Skype for Business Server 2015 での Windows PowerShell の操作の詳細については、「Insert introduction HERE」にある Skype for Business Server 管理シェルのドキュメントを参照してください。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Skype for Business Server 管理シェル スクリプトの実行について

負荷シミュレーションの準備に使用できるサンプル PowerShell スクリプトを提供しています。 これらのスクリプトは読み込みシミュレーションを目的とします。このため、これらのスクリプトは単純で制限が少ない場合があります。 これは、ご使用の実稼働環境には適していない場合があります。 繰り返しになりますが、これらのスクリプトはサンプルです。実際に使用する前に、スクリプトを確認する必要があります。多くの場合、環境に関連する変更を加えます。 少なくとも、(エージェント グループに割り当てられているエージェントを指定するために) トポロジを念頭に置いて応答サービス グループ (RSG) スクリプトを変更する必要があります。 ただし、必要ない場合は、このコマンドを実行する必要があります。
  
> [!CAUTION]
> これらのサンプルの確認と理解に注意してください。 スクリプトは、実行時にトポロジ内の既存の設定を上書きします。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Stress and Performance Tool クライアントのバージョン名

以前に既定値から設定を変更した場合は、クライアント バージョン チェック ポリシーの構成が必要になる場合があります。 不明な場合は、クライアント バージョン チェックのドキュメント [を確認してください](https://msdn.microsoft.com/vsto/jj923060)。
  
Stress and Performance Tool は、Skype for Business Server 2015 と通信するときに、既定で次のユーザー エージェント バージョンを使用します。
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
LyncPerfTool の Mobility (UCWA) クライアントの場合:
  
- UCWA Perf ツール/Web 会議
    
- UCWA Perf ツール/モバイル
    

