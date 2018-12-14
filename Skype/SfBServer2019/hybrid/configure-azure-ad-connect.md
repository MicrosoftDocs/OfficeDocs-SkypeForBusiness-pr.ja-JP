---
title: Azure AD を構成する接続
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: ハイブリッド環境で Azure AD 接続の構成方法の詳細については。
ms.openlocfilehash: a63f5bde6db1f9d04e2a1fbf03dd4434d1b7c8b3
ms.sourcegitcommit: a3181bc3707b09c1e3f87c343b38259fdc6dabd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "27264926"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Azure を構成する AD がビジネスのチームと Skype の接続
 
Skype ビジネス サーバー (または、Lync Server) の設置があり、オンライン ビジネスのチームまたは Skype のいずれかを使用する計画は人の組織はこれで説明するよう Office 365 では、その設置ディレクトリと同期するのには、Azure の AD 接続を構成しなければなりませんドキュメント。  チーム設置型のビジネスに Skype から直接移動する組織が含まれます。 具体的には、Skype で設置型のビジネスの組織では、Azure AD に適切な msRTCSIP の属性が同期されている必要がありますを確認します。 

> [!NOTE]
> 設置型のビジネスで Skype を持っている既存のチームのユーザーは、Skype をビジネスの設置型のアカウントなど、ビジネス ユーザーのために、Skype での相互運用機能のフル機能-を取得するのにはクラウドに移行の必要があります。フェデレーション組織のユーザーと通信します。 でも、ユーザーのみを使用する場合のチーム、インフラストラクチャによって追加機能を提供するこのオンラインの Skype のビジネス アカウントが必要です。  この移行を実行するには、ハイブリッドを有効にすることができるように、AD の Azure の接続が正しく構成されていることを確認する必要があります。
 

## <a name="background-information"></a>バック グラウンド情報

Azure Active Directory 接続すると、Office 365 と同期して継続的に、オンプレミスの Active Directory が維持されます。  設置ディレクトリは、id の権限のあるソースと、Azure AD に、オンプレミス環境からの変更が同期されます。 詳細については、 [AD の Azure 接続の同期](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)を参照してください。 設置とオンラインのユーザーとの間の通信を確保する Azure AD に設置型のオンライン ビジネスのチーム、設置型のビジネス、Skype または Skype を使用するすべてのユーザーを同期させる必要がある場合でも、移行しないすべてのユーザー、オンプレミスからクラウドに移行する、. *組織内のユーザーは、オンプレミスとオンライン ディレクトリの両方で表されます。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>ビジネス サーバーの Skype がある場合、Azure AD を構成します。 

オンプレミス Active Directory フォレストが 1 つまたは複数のフォレストがある場合は、かどうかは、さまざまな[AD の Azure の接続のトポロジ](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)で説明したように、サポートされているトポロジで Azure AD 接続を使用できます。  Skype ビジネス サーバーの観点からは、次の 3 つの主要なバリエーションがあります。 

1. 単一フォレスト、権限のあるユーザーの id が含まれていますし、Skype をビジネスのサーバーをホストします。 

2. Skype をビジネスのサーバーのホストの 1 つだけ、複数のフォレストと 1 つまたは複数他のフォレストに権限のあるユーザーの id (アカウント フォレスト) が含まれています。 

3. Skype の複数の展開の複数のフォレスト内のビジネスのサーバーです。 特定の要件を満たしていれば、組織は 1 つの Office 365 テナントにこれら複数の展開を統合できます。

### <a name="single-forest"></a>単一のフォレスト 

場合はユーザー アカウント、ビジネス用の Skype はすべて単一のフォレストでホスト、Azure AD に、このフォレストのユーザーを同期するのには、Azure AD 接続が構成されていることを確認する必要があります。  Azure AD 接続のインストール ウィザードには、さまざまなオプションがいますが、適切な属性は Azure Active Directory に自動的に同期されます。 お客様は、組み込みの同期ルールや (これは可能ですが、インストール ウィザードではありません) 構成を管理するためのコネクタを変更することをお勧めします。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>ビジネスの展開の 1 つの Skype での複数のフォレスト 

このシナリオは、リソース フォレスト トポロジとも呼ばれます。 ユーザーの権限のあるユーザーが 1 つまたは複数のアカウントのフォレストでホストされているし、ビジネス用の Skype は別のリソース フォレストの展開 (それ自体がまたホスト権限のあるユーザーの id) です。 一般に、ビジネス ユーザーの権限を持つユーザーの Skype は、Skype のビジネス サーバーと同じフォレスト内、または別のフォレストの提供します。 

- アカウントの forest(s) からの権限のある id を持つユーザーは、リソース フォレスト (Skype ビジネス サーバーを配置する場所) で、無効なユーザー オブジェクトとして表されますと、リソース フォレスト内の msRTCSIP OriginatorSID 属性には、SID が一致する、。アカウント フォレストです。 詳細については、[ハイブリッド ビジネスの Skype の複数のフォレスト環境の構成](configure-a-multi-forest-environment-for-hybrid.md)を参照してください。

- Skype ビジネス サーバーをホストしているリソース フォレストの信頼アカウント forest(s) をします。  

- Azure AD 接続を使用して正しい値を使用して AD を Azure には、すべての関連するユーザー オブジェクトと (アカウント フォレスト) からの両方の id の属性 (リソース フォレスト) からビジネス用の Skype が同期されます。  

 適切なオブジェクトと属性の[複数のフォレストの設置型のシナリオ](configure-a-multi-forest-environment-for-hybrid.md)での Azure AD 同期化を達成するため、強くお勧め Azure AD 接続を使用してユーザー アカウントを有効にしているすべてのフォレストからフォレストを同期します。ビジネス用の Skype が含まれています。  すべてのフォレストから同期を実行すると仮定した場合、これらの id をマージし、Azure AD への同期の Azure AD 接続し、構成しなければなりません。 Azure AD 接続では、このシナリオを処理するよう設計されていて、識別情報を結合するのにはアンカーの設定を含む、これを設定するのには、インストール ウィザードのオプションが組み込まれたを提供します。  次の選択: ユーザーの id が複数のディレクトリに存在します。 使用して一致は・ ObjectSID、msExchangeMasterAccountSID 属性です。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>ビジネス サーバー展開では複数のフォレストに複数の Skype 

このシナリオでは、複数のフォレスト、それぞれ含まれている Skype をビジネス サーバー、および 1 つの Office 365 テナントがあります。  ビジネスのサーバーの Skype を含む各フォレストは、AAD の接続を使用してテナントの Azure AD に同期できます。 多くても 1 つのフォレストを構成できます Skype のビジネスのハイブリッドの特定の時点で。 フォレスト内のハイブリッドを有効にする前に他のすべてのフォレストからのすべての SIP ドメインする必要があります無効にする[無効にする csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)を使用します。 Office 365 にこのような環境を統合する方法の詳細については、[チームおよびビジネス用の Skype のためのクラウドの統合](cloud-consolidation.md)を参照してください。

## <a name="general-requirements"></a>全般的な要件 

チームとビジネスのオンライン サービスの Skype は、適切な Active Directory 属性が存在し、Azure AD で設定されている必要があります。  マイクロソフトの一般的な推奨事項では、Skype を含むビジネスのサーバーのすべてのフォレストと、ユーザーの id を含むすべてのフォレストを同期します。

 複数のフォレスト間のユーザーの id がある場合、Azure AD 接続は、差し込み印刷を行ってください。 場合はこのガイドは、Azure AD 接続が自動的に同期する適切な属性では、[コネクタ] または [Azure AD 接続で同期規則を変更しない限り。 
  
ユーザー id およびビジネス サーバー配置の Skype を含むすべてのフォレストから同期しない場合は、関連する id をまだことを確認する必要があり、チームまたは Skype を使用してすべてのユーザーは Azure の AD には、Skype のビジネスの属性は設定が正しくビジネスの (かどうかの設置型またはオンライン)--追加する必要可能性がありますが、オンプレミス ディレクトリ同期します。 詳細についてを参照してください[Azure AD 接続の同期: 属性は、Azure Active Directory に同期させる](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)です。

このような状況では、Azure AD に属性を設定しての設定が正しいことを確認する責任はお客様がします。 以下の点について留意してください。 

- オンライン ディレクトリにデータの破損が発生する可能性がありますが、正しくない構成できてしまうために、Azure AD に同期するための標準構成を使用することは危険です。

- 製品の出現に伴い、マイクロソフトは標準的な同期の構成に関連するすべてのフォレストを同期することを確認するのには継続します。 カスタムの同期の構成でのお客様は、その構成を Azure AD に適切な属性と値を提供することを保証します。 

## <a name="related-information"></a>関連情報

- [ハイブリッドの id とは何です。](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD 接続の同期: 理解し、同期をカスタマイズします。](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD のトポロジを接続します。](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD 接続の同期: Azure Active directory 属性の同期](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
