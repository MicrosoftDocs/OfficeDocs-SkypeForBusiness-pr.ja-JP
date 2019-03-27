---
title: Office 365 で Skype for Business クライアントを展開する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. '
ms.openlocfilehash: 6dccd022d82519c1dfdce13f767e5b0a2531eb10
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896795"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Office 365 で Skype for Business クライアントを展開する

この資料は、**[管理者](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)** では、配置方法ビジネス アプリケーションの Skype ユーザーに、組織内のオプションについて説明します。
  
ビジネス ユーザーは、Skype を展開する前に、[オンライン ビジネスの Skype の設定](set-up-skype-for-business-online.md)資料では、手順 1 ~ 3 を行っています。 これによって、ご使用のドメインで Skype for Business がセットアップされ、すべてのユーザーにライセンスが割り当てられ、組織用に IM と[Skype for Business Online でプレゼンスを設定する](configure-presence-in-skype-for-business-online.md)が構成されます。
  
> [!NOTE]
> ユーザーが Skype for Business アプリをインストールするためには、PC またはデバイス上のローカル管理者である必要があります。 または、PC またはデバイスにアプリをインストールできるローカル グループのメンバーであることが必要です。 ユーザーが自分のデバイスにソフトウェアをインストールするのには許可されていない場合は、それらのビジネス アプリケーションの Skype をインストールする必要があります。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>ほとんどの中小規模の企業の場合

 **ステップ バイ ステップのインストール手順:** 小規模または中規模のビジネスがある場合は、単に自分の PC 上のビジネス アプリケーションの Skype をインストールするのには、ユーザーに依頼することをお勧めします。 次の手順を参照するように:[ビジネスの Skype をインストール](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US)します。 Mac を使用している場合は、 [Office 365 の Mac の 2011 年の Lync をセットアップ](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US)することをポイントします。 ビジネス アプリケーションの Skype は、Office アプリケーションの残りの部分から個別にインストールします。
  
 **Office 365 ProPlus のお客様:** お客様の会社で E3 プランなどの Office 365 ProPlus が含まれる Office 365 プランを使用している場合、ユーザーが Word、Excel、PowerPoint などをダウンロードしてインストールすると、同時に Skype for Business アプリがインストールされます。つまり、Office をすべてアンインストールしないと Skype for Business をアンインストールできません。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>ユーザーが Skype for Business を利用できるようにするかどうかを選択する

[管理者](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)として、ユーザーがビジネス アプリケーションの Skype を使用できるようにするかどうかを選択できます。
  
- **ソフトウェアを取得するかどうか、社内のすべてのユーザーを制御する**: にサインインするのに、Office 365 の管理センター、**ソフトウェアをインストール**するには、およびユーザーの利用可能にソフトウェアを選択します。
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **制御するかどうか、会社内の特定のユーザー ソフトウェアを入手する**: にサインインするのに、Office 365 の管理センターは、**ユーザー**に > 、**アクティブなユーザー**が、ソフトウェアにアクセスできるようにし人を選択し、し、[**編集**] をクリックして**製品ライセンス**の横にあるし、ライセンスを有効または無効にします。
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 新しい Office 365 管理センター _gt**ユーザー**にサインインする必要があるどのような計画は、組織内のユーザーに割り当てられて、か > **アクティブなユーザー**です。リストからユーザーを選択し、**製品のライセンス**の下を確認します。従来の Office 365 管理センターを使用する場合は、**割り当てられたライセンス**の下で確認します。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>ユーザーに Skype for Business を手動で展開する
<a name="bkmk_manual_1"> </a>

If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files. To do this go to the **Manually deploy user software** section of the Office 365 admin center. You can then select **Install** and save the setup .exe file to a network location.
  
別のオプションでは、ユーザーのビジネスの基本的なアプリケーションの Skype をダウンロードします。 [ビジネス基本 (32 または 64 ビット) 用の Microsoft の Skype](https://www.microsoft.com/en-us/download/details.aspx?id=49440)をダウンロードすることができます。
  
Skype for Business アプリのフル バージョンの場合も Basic バージョンの場合も、セットアップ ファイルをダウンロードしたら、セットアップ プログラムを実行してコンピューターにアプリをインストールできるよう、ネットワーク パスをユーザーに手動で (たとえばメールなどで) 送信する必要があります。
  
また、既存のソフトウェア展開ツールとプロセスを使用することで、これらのダウンロードを使用して Skype for Business アプリをユーザーに展開することもできます。
  
## <a name="for-larger-and-enterprise-organizations"></a>大規模組織と企業の場合

> [!NOTE]
> このセクションの内容が該当するのは、Office 365 プランで使用可能な Skype for Business アプリのみです。組織で、Windows インストーラー ベース (MSI) である、Skype for Business アプリのボリューム ライセンス バージョンを使用している場合は、「[Skype for Business Server 2015 でクライアント インストールをカスタマイズする](https://technet.microsoft.com/en-us/library/jj204934.aspx)」をご覧ください。 
  
多くの大企業や大規模な組織では、ユーザーは自分のコンピューターにソフトウェアをインストールすることを許可されていません。代わりに、IT 部門が必要なソフトウェアをユーザーのコンピューターに展開します。また IT 部門は、組織で使用されるインターネットまたはネットワークの帯域幅を制御するために、遠くのインターネットや企業ネットワークからではなく、ネットワーク上の近くの場所からソフトウェアをインストールする必要があります。
  
Office 365 からインストールされているかを制御する場合は、Skype のビジネス アプリケーションを展開するためのいくつかのオプションがあります。これらのオプションの一部を以下に示します。
  
- 「[ユーザーに Skype for Business を手動で展開する](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)」に記載されているように、Office 365 管理センターからローカル ネットワークに Skype for Business アプリをダウンロードします。
    
- **[Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)** を使用して、Office 365 ProPlus または Skype for Business アプリをローカル ネットワークにダウンロードします。次に、Office 展開ツールを使用してユーザーにアプリを展開します。Office 展開ツールでは、言語やバージョン (32 ビット/64 ビット) など、展開の特定の側面を制御できます。
    
- System Center Configuration Manager などの既存のソフトウェア展開ツールやプロセスを使用して、Office 365 ProPlus または Skype for Business アプリをユーザーに展開します。[Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)や、Office 365 管理センターからダウンロードしたソフトウェアと、既存のツールおよびプロセスを併用できます。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Office 展開ツールの使用法に関する詳細情報

Office 展開ツールのダウンロードの詳細および Skype for Business アプリとその他の Office 365 クライアント アプリのインストールの詳細については、「[Office 365 でユーザーのソフトウェアを管理する](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360)」を参照してください。
  
Office の展開ツールを使用してアプリケーションを展開するに関連する手順の概要を以下に示します。
  
1. **[最新の Office 展開ツールをダウンロード](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** します。
    
2. Office 展開ツールで使用する configuration.xml ファイルを作成します。設定やバージョン (32 ビットまたは 64 ビット)、インストール言語など、必要なクライアント アプリの設定を指定します。
    
3. Office 展開ツールと configuration.xml ファイルを使用して、Office コンテンツ配信ネットワーク (CDN) からセットアップ ファイルをローカルまたは社内のネットワークにダウンロードします。
    
4. Office 展開ツールと configuration.xml を使用して、Skype for Business アプリなど Office クライアント アプリをインストールします。
    
Office 展開ツールおよび configuration.xml ファイルの使用法の詳細については、次の記事を参照してください。
  
- [クイック実行用 Office 展開ツール](https://technet.microsoft.com/library/jj219422.aspx)
    
- [クイック実行 configuration.xml ファイルのリファレンス](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>System Center Configuration Manager の使用法に関する詳細情報

System Center Configuration Manager など、既存のソフトウェア展開ツールおよびプロセスを使用して、Skype for Business アプリを展開することができます。これらのツールおよびプロセスと、Office 365 管理センターからダウンロードしたソフトウェアや、Office 展開ツールを併用できます。
  
Configuration Manager を使用したソフトウェアの展開の詳細については、次の記事を参照してください。
  
- [Configuration Manager でのアプリケーションの作成方法](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [Configuration Manager でのアプリケーションの展開方法](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Office 365 ProPlus の展開の一環として Skype for Business アプリを展開する場合は、「[System Center Configuration Manager を使用して Office 365 ProPlus を展開する](https://technet.microsoft.com/en-us/library/dn708063.aspx)」をご覧ください。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Skype for Business アプリに対する更新プログラムの計画

Skype for Business アプリの展開の一環として、Skype for Business のインストール後に更新プログラムを取得する方法を考慮する必要があります。これらの更新プログラムには、新機能、セキュリティ更新プログラム、安定性やパフォーマンスを改善するセキュリティ以外の更新プログラムが含まれます。考慮する必要がある 2 つの主な事項は、次のとおりです。
  
- 更新プログラムを取得する場所
    
- 機能の更新プログラムを取得する頻度
    
更新プログラムの取得元、および機能の更新プログラムを取得する頻度は制御できますが、取得する特定のセキュリティ更新プログラムやセキュリティ以外の更新プログラムを選ぶことはできません。
  
 **更新プログラムの取得元**
  
既定では、Skype for Business アプリがインストールされると、更新プログラムが Microsoft から提供されていれば、インターネットから自動的にダウンロードされます。更新プログラムを適用する頻度または更新プログラムのインストール元をより詳細に制御したい場合は、Office 展開ツールまたはグループ ポリシーを使用して構成することができます。
  
たとえば、多くの組織では、組織全体に展開する前にユーザー グループで更新プログラムをテストする必要があります。これを行うには、Office 展開ツールまたはグループ ポリシーを使用して、インターネットから自動で取得する代わりにネットワーク上の特定の場所から更新プログラムを取得するように、Skype for Business アプリを構成する方法があります。次に、Office 展開ツールを使用して、ローカル ネットワークに更新プログラムを毎月ダウンロードできます。
  
Office 365 ソフトウェアに対する更新プログラムの動作の詳細については、次の記事をご覧ください。
  
- [Office 365 ProPlus の更新プロセスの概要](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Office 365 用リソースへの更新を管理する方法を選択します。](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Office 365 ProPlus の更新設定を構成する](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
  **機能の更新プログラムを取得する頻度**
  
更新プログラムの取得元に加えて、Skype for Business クライアントの新機能を取得する頻度を制御することもできます。次の 2 つの選択肢があります。
  
- 新機能がある場合に、月ごとに機能の更新プログラムを取得する
    
- 6 か月ごとに機能の更新プログラムを取得する
    
組織によっては、新機能をテストする必要があるため、機能の更新プログラムの取得を毎月ではなく年 2 回に限定しています。
  
Office 展開ツールまたはグループ ポリシーを使用して更新チャネルを構成することで、機能の更新プログラムを取得する頻度を制御できます。月次チャネルでは機能の更新プログラムが毎月提供されますが、半期チャネルではおよそ 6 か月ごとに機能の更新プログラムが提供されます。チャネルの詳細については、「[Office 365 ProPlus 更新プログラム チャネルの概要](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)」をご覧ください。
  
## <a name="related-topics"></a>関連項目

[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)
  
[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
