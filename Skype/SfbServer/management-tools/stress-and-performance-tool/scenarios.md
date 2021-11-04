---
title: 2015 年Skype for Business Serverパフォーマンス ツールのパフォーマンス シナリオ
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: ストレスとパフォーマンス ツールを使用して、パフォーマンスSkype for Business Serverテストを行う 2015 年を構成するために必要なタスク。
ms.openlocfilehash: a56e2ec12547937ef44973932ef79d3405573039
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777257"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>2015 年Skype for Business Serverパフォーマンス ツールのパフォーマンス シナリオ
 
ストレスとパフォーマンス ツールを使用して、パフォーマンスSkype for Business Serverテストを行う 2015 年を構成するために必要なタスク。
  
Skype for Business Server 2015 ストレスとパフォーマンス ツール (LyncPerfTool) を実行するには、Skype for Business Server 2015 トポロジを最初に、関連するシナリオ用に構成する必要があります。 2015 Skype for Business Server構成されていない場合、または正しく構成されていない場合、負荷シミュレーションが失敗する可能性が非常に高い。 2015 Skype for Business Serverストレスとパフォーマンス ツールでは、ツールのダウンロードの一環として、Skype for Business Server 管理シェル スクリプトと基本的なリソース ファイルの例[を提供しています](https://www.microsoft.com/download/details.aspx?id=50367)。 これらは、展開を構成するための開始点としてSkype for Business Serverできます。 この記事では、提供されるWindows PowerShellについて説明します。
  
> [!NOTE]
> このトピックでは、2015 年を構成する方法Skype for Business Server、その他の計画と展開に関するトピックがあります。 2015 年 2015 年Windows PowerShellのSkype for Business Server詳細については、「Insert introduction HERE」の「Skype for Business Server管理シェル」のドキュメントを参照してください。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>管理シェル Skype for Business Serverの実行について

負荷シミュレーションの準備に使用できる PowerShell スクリプトのサンプルを提供しています。 これらのスクリプトは読み込みシミュレーションを目的としますので、単純で透過的なスクリプトが見つかるはずです。 これは、実稼働環境に適していない場合があります。 繰り返しますが、これらのスクリプトはサンプルであり、それらを確認する必要があります。多くの場合、それらを実際に使用する前に環境に関連する変更を加えます。 少なくとも、トポロジを念頭に置いて応答サービス グループ (RSG) スクリプトを変更する必要があります (エージェント グループに割り当てられたエージェントを指定する場合)。 ただし、実行する必要がなき場合は実行する必要があります。
  
> [!CAUTION]
> これらのサンプルの確認と理解に注意してください。 スクリプトは、実行時にトポロジ内の既存の設定を上書きします。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>ストレスとパフォーマンス ツールのクライアント バージョン名

以前に既定値から設定を変更した場合は、クライアント バージョン チェック ポリシーの構成が必要になる場合があります。 この問題について不明な場合は、クライアント バージョン チェック [のドキュメントを確認してください](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules)。
  
ストレスとパフォーマンス ツールは、2015 年から 2015 年に通信するときに、既定で次のユーザー エージェント Skype for Business Serverします。
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 ストレスおよびパフォーマンス ツール)
    
- OCPHONE/.0.522
    
LyncPerfTool のモビリティ (UCWA) クライアントの場合:
  
- UCWA Perf ツール/Web 会議
    
- UCWA Perf Tool/Mobile
