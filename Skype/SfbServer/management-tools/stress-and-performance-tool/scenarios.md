---
title: Skype for Business Server 2015 ストレスとパフォーマンス ツールのパフォーマンス シナリオ
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
description: ストレスとパフォーマンス ツールを使用して、パフォーマンスと負荷テストを行う Skype for Business Server 2015 を構成するために必要なタスク。
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105373"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 ストレスとパフォーマンス ツールのパフォーマンス シナリオ
 
ストレスとパフォーマンス ツールを使用して、パフォーマンスと負荷テストを行う Skype for Business Server 2015 を構成するために必要なタスク。
  
Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool) を実行するには、まず、自分に関連するシナリオ用に Skype for Business Server 2015 トポロジを構成する必要があります。 Skype for Business Server 2015 が構成されていないか、正しく構成されていない場合、負荷シミュレーションが失敗する可能性が非常に高い。 Skype for Business Server 2015 ストレスとパフォーマンス ツールでは、ツールのダウンロードの一環として、Skype for Business Server 管理シェル スクリプトと基本的なリソース ファイルの例を [提供しています](https://www.microsoft.com/download/details.aspx?id=50367)。 これらは、Skype for Business Server 展開を構成するための開始点として使用できます。 この記事では、提供されるWindows PowerShellについて説明します。
  
> [!NOTE]
> このトピックでは、Skype for Business Server 2015 を一般的に構成する方法については説明しません。その他の計画と展開に関するトピックがあります。 Skype for Business Server 2015 Windows PowerShellの操作の詳細については、「Insert introduction HERE」の「Skype for Business Server Management Shell」のドキュメントを参照してください。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>Skype for Business Server 管理シェル スクリプトの実行について

負荷シミュレーションの準備に使用できる PowerShell スクリプトのサンプルを提供しています。 これらのスクリプトは読み込みシミュレーションを目的としますので、単純で透過的なスクリプトが見つかるはずです。 これは、実稼働環境に適していない場合があります。 繰り返しますが、これらのスクリプトはサンプルであり、それらを確認する必要があります。多くの場合、それらを実際に使用する前に環境に関連する変更を加えます。 少なくとも、トポロジを念頭に置いて応答サービス グループ (RSG) スクリプトを変更する必要があります (エージェント グループに割り当てられたエージェントを指定する場合)。 ただし、実行する必要がなき場合は実行する必要があります。
  
> [!CAUTION]
> これらのサンプルの確認と理解に注意してください。 スクリプトは、実行時にトポロジ内の既存の設定を上書きします。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>ストレスとパフォーマンス ツールのクライアント バージョン名

以前に既定値から設定を変更した場合は、クライアント バージョン チェック ポリシーの構成が必要になる場合があります。 この問題について不明な場合は、クライアント バージョン チェック [のドキュメントを確認してください](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules)。
  
ストレスとパフォーマンス ツールは、Skype for Business Server 2015 と通信するときに、既定で次のユーザー エージェント バージョンを使用します。
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
LyncPerfTool のモビリティ (UCWA) クライアントの場合:
  
- UCWA Perf ツール/Web 会議
    
- UCWA Perf Tool/Mobile
