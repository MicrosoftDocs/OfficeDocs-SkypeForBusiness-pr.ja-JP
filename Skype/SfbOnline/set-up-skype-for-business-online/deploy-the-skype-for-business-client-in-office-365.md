---
title: "Skype for Business のクライアントでは、Office 365 を展開します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "計画および小規模、中、および大規模の組織にユーザーが使用できるようにで Skype for Business を展開する方法について説明します。 "
ms.openlocfilehash: 5a3af14d7bf507a50ab7d007a066e3bd42d90c50
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Skype for Business のクライアントでは、Office 365 を展開します。

この記事では、組織で、ユーザーに Skype for Business アプリを展開する、**[管理者](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**には、方法のオプションについて説明します。
  
ビジネス、ユーザーが確認用に Skype を展開する前に、 [Skype for Business Online を設定する](set-up-skype-for-business-online.md)記事の手順 1 ~ 3 を行っています。この方法では、Skype for Business ように設定されます自分のドメインで、そのライセンスでは、すべてのユーザーが表示されますが構成した IM と[Skype for Business Online でプレゼンスを設定](configure-presence-in-skype-for-business-online.md)、組織のします。
  
> [!NOTE]
> ユーザーが Skype for Business アプリをインストールするのには、他のユーザーの PC またはデバイスにローカルの管理者にする必要。または、ローカルのコンピューターまたはデバイスにアプリをインストールできるグループの一部にする必要があります。ユーザーはいないソフトウェアをインストール、デバイスで許可されている場合に Skype for Business アプリをインストールする必要があります。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>ほとんどの小規模および中規模企業

 **ステップ バイ ステップのインストール手順:**中小規模のビジネスを使っている場合は、ユーザーが自分のコンピューターで Skype for Business アプリをインストールするだけでメッセージをお勧めします。次の手順を参照するように: [Skype for Business をインストール](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US)します。Mac を使っている場合は、 [Lync for Office 365 for Mac 2011 をセットアップ](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US)することをポイントします。Office アプリの残りの部分から Skype for Business アプリを個別にインストールします。
  
 **顧客の office 365 ProPlus:**ビジネスを E3 プランなど、Office 365 ProPlus を含む Office 365 プランを使用している場合は、同時に、ユーザーがダウンロードして、Word、Excel、PowerPoint などをインストールする Skype for Business アプリがインストールされています。また、すべての Office をアンインストールした場合を除き、Skype for Business をアンインストールすることはできません。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>ユーザーに Skype for Business を使用できるようにするかどうかを選択します。

[管理者](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)は、ユーザーに Skype for Business アプリを使用できるようにするかどうかを選択できます。
  
- **本ソフトウェアを取得するかどうか、会社のすべてのユーザーを制御する**: office 365 管理センターにサインインし、**ソフトウェアをインストール**してに移動して、[ソフトウェアをユーザーに利用できるようにする] を選びます。
    
    ![社内のユーザーが利用できるようにするソフトウェアを選びます。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **制御するかどうか、社内の特定のユーザー ソフトウェアを取得する**: にサインインする Office 365 管理センターで、**ユーザー**に移動 > **アクティブなユーザー**の場合がソフトウェアに、アクセスを許可する人を選択し、[**編集**] をクリックして**製品のライセンス**の横にあると、ライセンスを有効または無効にします。
    
    ![ユーザーにアクセスするソフトウェアを選びます。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> どのようなプランが、組織内のユーザーに割り当てられている必要がある場合、新しい Office 365 管理センターへのサインイン >**ユーザー** > **アクティブなユーザー**。リストからユーザーを選択し、[**製品のライセンス**を確認します。従来の Office 365 管理センターを使用している場合は、[**割り当て済みのライセンス**を確認します。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>ユーザーに Skype for Business を手動で展開します。
<a name="bkmk_manual_1"> </a>

ユーザーがインターネットからの代わりに、ネットワーク上の場所から Skype for Business アプリをインストールする場合は、セットアップ ファイルをダウンロードできます。Office 365 管理センターの [**ユーザー ソフトウェアを手動で配置**] セクションに移動を行う。**インストール**] を選択し、ネットワーク上の場所にセットアップ .exe ファイルを保存します。
  
別の方法として、Skype for Business の基本的なユーザー アプリをダウンロードします。[Microsoft Skype for Business 基本的な (32 または 64 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=49440)をダウンロードすることができます。
  
両方全体で基本的な Skype for Business アプリをセットアップ ファイルをダウンロードした後にする必要が手動で (たとえば、メールで送信する)、ネットワーク パス、ユーザーにアプリをインストールして、自分のコンピューターでセットアップ プログラムを実行できるようにします。
  
これらのダウンロードを使って、既存のソフトウェア展開ツールとプロセスを使用して、ユーザーに Skype for Business アプリを展開することもできます。
  
## <a name="for-larger-and-enterprise-organizations"></a>拡大と企業

> [!NOTE]
> このセクションでは、Skype for Business アプリを利用して Office 365 プランにのみ適用されます。For Business アプリは、Windows インストーラー (MSI) にすると、組織が Skype のボリューム ライセンス版を使用する場合は、 [Skype for Business Server 2015 でユーザー設定のクライアントのインストール](https://technet.microsoft.com/en-us/library/jj204934.aspx)を参照してください。 
  
多くの企業または大規模の組織では、ユーザーは、各自のコンピューターにソフトウェアをインストールする使用できません。代わりに、IT 部門は、ユーザーのコンピューターに必要なソフトウェアを展開します。IT 部門することも、インターネット経由で内または企業ネットワークからの代わりに、ネットワーク上の近くにある場所からソフトウェアをインストールする必要があるために、組織で使用されるインターネットまたはネットワークの帯域幅の量を制御します。
  
、Office 365 でからインストールされているかを制御する場合は、Skype for Business アプリを展開するためのいくつかのオプションがあります。これらのオプションの一部を以下に示します。
  
- [手動で Skype for Business をユーザーに展開する](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)で説明するように、Office 365 管理センターからローカル ネットワークに Skype for Business アプリをダウンロードします。
    
- **[Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)**を使用すると、ローカル ネットワークに、Office 365 ProPlus または Skype for Business アプリをダウンロードします。次に、Office 展開ツールを使用して、アプリをユーザーに展開します。Office 展開ツールを使用する言語バージョン (32 ビットまたは 64 ビット) などの展開の一部を制御することができます。
    
- Office 365 ProPlus または Skype for Business アプリをユーザーに展開するのに、既存のソフトウェア展開ツールと、システム センター構成マネージャーなど、プロセスを使用します。[Office 展開ツール](https://go.microsoft.com/fwlink/p/?LinkID=626065)を使用して、または Office 365 管理センターからダウンロードしたソフトウェアを使って、既存のツールとプロセスを使用することができます。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Office 展開ツールを使用してさらに詳しい情報

Office 展開ツールと Skype for Business アプリと他の Office 365 クライアント アプリケーションをインストールする方法についてのダウンロードの詳細については、 [Office 365 で管理するユーザーのソフトウェア](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360)を参照してください。
  
Office 展開ツールを使用して、アプリの展開に含まれる手順の概要を次に示します。
  
1. Microsoft ダウンロード センターから**[最新の Office 展開ツールをダウンロード](https://www.microsoft.com/en-us/download/details.aspx?id=49117)**をします。
    
2. バージョン (32 ビットまたは 64 ビット)、インストール言語などの設定などの必要なクライアント アプリケーションの設定を含む Office 展開ツールを使用する configuration.xml ファイルを作成します。
    
3. Office 展開ツールと configuration.xml ファイルを使用すると、Office コンテンツ配信ネットワーク (CDN) から、ローカルまたは内部ネットワークにセットアップ ファイルをダウンロードします。
    
4. Office 展開ツールを使用して、configuration.xml Skype for Business アプリを含む、Office クライアント アプリケーションをインストールします。
    
Office 展開ツールと configuration.xml ファイルの使用に関する詳細については、次の記事を参照してください。
  
- [Office 展開ツールの概要](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml 設定](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>システム センター構成マネージャーを使用してさらに詳しい情報

Skype for Business アプリを展開するのには、システム センター構成マネージャーなど、プロセス、既存のソフトウェア展開ツールを使用できます。いずれかのソフトウェア、Office 365 管理センターからダウンロードすることで、または Office 展開ツールを使用して、これらのツールとプロセスを使用することができます。
  
構成マネージャーを使用して、ソフトウェアを展開する方法の詳細については、次の記事を参照してください。
  
- [構成マネージャーのアプリケーションを作成する方法](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [アプリケーション構成マネージャーで配置する方法](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Skype for Business アプリを一部としてを展開しているかどうかは Office 365 ProPlus の展開][展開する Office 365 ProPlus システム センター構成マネージャーを使用して、](https://technet.microsoft.com/en-us/library/dn708063.aspx)参照してください。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Skype for Business アプリの更新プログラムの計画

Skype for Business アプリの展開の一部として、Skype for Business をインストールした後、更新プログラムを入手する方法を考慮する必要があります。次の更新プログラムには、新機能やセキュリティ更新プログラム、安定性とパフォーマンスの向上を提供する更新プログラムなど、セキュリティ以外の更新を含めることができます。2 つの主なことを検討する必要があります。
  
- 更新プログラムを入手する場所
    
- 機能の更新プログラムを入手する頻度
    
更新を取得して、機能の更新プログラムを入手する頻度を制御できますが、中に特定のセキュリティ更新プログラムまたはセキュリティ以外の更新を取得するを選択することはできません。
  
 **更新プログラムを入手する場所**
  
既定では、Skype for Business アプリがインストールされたら、更新プログラムは自動的にインターネットからダウンロードする、Microsoft から公開されたらします。場合は、その他のコントロールに更新されると、またはからの更新プログラムがインストールされている場合を構成するのには、Office 展開ツールまたはグループ ポリシーを使用することができます。
  
たとえば、多くの組織が組織全体で展開する前にユーザーのグループと更新プログラムをテストするとします。Office 展開ツールまたはグループ ポリシーを使用して、インターネットから自動的の代わりに、ネットワーク上の特定の場所からの更新を取得する Skype for Business アプリを構成するのには、これを行うことができます。次に、ローカル ネットワークにすべての月の更新プログラムをダウンロードするのには、Office 展開ツールを使用することができます。
  
Office 365 のソフトウェアの更新プログラムの連携に関する詳細については、以下の記事を参照してください。
  
- [Office 365 ProPlus の更新プロセスの概要](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Office 365 ProPlus に更新を管理する方法を選ぶ](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Office 365 ProPlus の更新プログラムの設定を構成します。](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 **機能の更新プログラムを入手するには、頻度**
  
場所からの更新を取得、に加えて Skype for Business クライアントの新機能を取得するどのくらいの頻度を制御することもできます。2 つの選択肢は次のとおりです。
  
- 新機能がある場合に、毎月の機能の更新を取得します。
    
- 6 か月ごとの機能の更新プログラムを取得します。
    
組織によっては、毎月のではなく年 2 回のみの機能の更新を取得する必要があるため、新機能をテストする時間が必要です。
  
機能の更新を取得する更新チャネルを構成するのには、Office 展開ツールまたはグループ ポリシーを使用して、どのくらいの頻度を制御することができます。6 か月ごとの更新プログラムおすすめする機能の更新プログラム毎月 (約) 半年チャネルを使用するときに、毎月のチャンネルを使用します。チャンネルの詳細については、 [Office 365 ProPlus の更新プログラムのチャンネルの概要](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)を参照してください。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business Online をセットアップします。](set-up-skype-for-business-online.md)
  
[Skype Business および Microsoft チーム アドオン ライセンスを許可します。](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  

