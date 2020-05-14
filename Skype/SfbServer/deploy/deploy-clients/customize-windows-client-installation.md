---
title: Skype for Business Server で Windows クライアントインストールをカスタマイズする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: '概要: Skype for Business のインストール方法とツールの概要について説明します。'
ms.openlocfilehash: ea8a07bf6a6e00eee93f2a0a8b3ffc756b239ce9
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220837"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a>Skype for Business Server で Windows クライアントインストールをカスタマイズする
 
**概要:** Skype for business のインストール方法とツールの概要について説明します。
  
> [!NOTE]
> Microsoft 365 および Office 365 に同梱されている Skype for Business のインストールの詳細については、「 [microsoft 365 または office の365で skype For business クライアントを展開](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)する」を参照してください。 
  
エンタープライズ管理者は、このセクションで説明する方法を使用して、ボリュームライセンスバージョンの Windows インストーラーベース (.msi) インストールをカスタマイズできます。 すべてのカスタマイズオプションを提供する単一のツールはないため、Skype for Business の展開でこれらの方法を組み合わせて使用する可能性があります。 次のセクションで説明するツールを使用することができます。
  
- Skype for business [Server の Office カスタマイズツール (OCT) を使用](use-the-office-customization-tool-oct.md)して、Skype for business および他の Office プログラムの設定オプションと機能をカスタマイズします。
    
- Config.xml を使用して、 [Skype For Business Server のインストールタスクを実行](use-config-xml-to-perform-installation-tasks.md)し、ネットワークインストールポイントのパスを指定し、サイレントインストールを実行します。
    
- [Skype For Business Server のセットアップコマンドラインオプションを使用](use-setup-command-line-options.md)して、インストール時に使用する config.xml ファイルを指定します。
    
- グループポリシーオブジェクトエディター MMC スナップインを使用して、 [Skype For Business Server でクライアントブートストラップポリシーを構成](configure-client-bootstrapping-policies.md)します。
    
Office スイート製品を展開するときに構成するオプションは、おそらく他にもあります。 このセクションのトピックでは、これらのカスタマイズツールの概要と、Skype for Business に固有の考慮事項について説明します。 各ツールの詳細な Office ヘルプへのリンクもあります。 
  

