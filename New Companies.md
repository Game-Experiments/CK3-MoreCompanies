### 江南织造总局

地点：苏州/浙江/南京
服装厂、丝绸、棉花、艺术学院（可选）
+5 威望

名贵：品牌时装

```
# Jiangnan Weaving Bureaus
TRY_REPLACE:company_jiangnan_weaving_bureaus = {
	icon = "gfx/interface/icons/company_icons/historical_company_icons/company_jiangnan_weaving_bureaus.dds"
	background = "gfx/interface/icons/company_icons/company_backgrounds/comp_illu_manufacturing_light.dds"
	
	flavored_company = yes
	
	preferred_headquarters = { STATE_SUZHOU STATE_ZHEJIANG STATE_NANJING }
	
	possible_prestige_goods = {
		prestige_good_generic_uniforms
	}

	building_types = { #24
		building_textile_mill
		building_cotton_plantation
	}
	
	extension_building_types = {
		building_synthetics_plant
	}

	potential = {
		has_interest_marker_in_region = sr:region_south_china
	}
	
	attainable = {
		hidden_trigger = { # Hide attainable if it's always fulfilled by possible
			any_scope_state = {
				state_region = s:STATE_SUZHOU
				state_region = s:STATE_ZHEJIANG
				state_region = s:STATE_NANJING
			}
		}
	}
	
	possible = {
		any_scope_state = {
			state_region = s:STATE_SUZHOU
			state_region = s:STATE_ZHEJIANG
			state_region = s:STATE_NANJING
			is_incorporated = yes
			any_scope_building = {
				is_building_type = building_textile_mill
				level >= 5
			}
		}
	}
	
	prosperity_modifier = {
		country_prestige_mult = 0.02 #2
		country_influence_mult = 0.10
	}	
	

	ai_will_do = {
		has_technology_researched = chemical_bleaching
		any_scope_state = {
			OR = {
				state_region = s:STATE_SUZHOU
				state_region = s:STATE_ZHEJIANG
				state_region = s:STATE_NANJING
			}
			is_incorporated = yes
		}
	}

	ai_construction_targets = {
		building_silk_plantation = {
			level = 5
			state_trigger = {
				OR = {
					state_region = s:STATE_SUZHOU
					state_region = s:STATE_ZHEJIANG
					state_region = s:STATE_NANJING
				}
				is_incorporated = yes
			}
		}
		building_textile_mill = {
			level = 5
			state_trigger = {
				OR = {
					state_region = s:STATE_SUZHOU
					state_region = s:STATE_ZHEJIANG
					state_region = s:STATE_NANJING
				}
				is_incorporated = yes
			}
		}
	}

	ai_weight = {
		value = 3 # Higher base value for flavored companies
	}
}
```

### 工部矿务总局

地点：山西/河北
铁矿、煤矿、铁路（可选）
+
名贵：名贵铁

```
# Ministry of Works Mineral Resources Bureau
TRY_REPLACE:company_kaiping_mining = {
	icon = "gfx/interface/icons/company_icons/historical_company_icons/chinese_kaiping_mining_company.dds"
	background = "gfx/interface/icons/company_icons/company_backgrounds/comp_illu_mining.dds"

	flavored_company = yes

	preferred_headquarters = { STATE_SHANXI STATE_ZHILI }

	building_types = {
		building_iron_mine
		building_coal_mine
	}

	extension_building_types = {
		building_railway
	}
	
	possible_prestige_goods = {
		prestige_good_generic_iron
	}

	potential = {
		has_interest_marker_in_region = sr:region_north_china
	}

	attainable = {
		hidden_trigger = { # Hide attainable if it's always fulfilled by possible
			any_scope_state = {
				OR = {
					state_region = s:STATE_SHANXI
					state_region = s:STATE_ZHILI
				}
			}
		}
	}

	possible = {
		has_technology_researched = steam_donkey
		has_technology_researched = railways
		any_scope_state = {
			OR = {
				state_region = s:STATE_BEIJING
				state_region = s:STATE_ZHILI
			}
			is_incorporated = yes
			any_scope_building = {
				is_building_type = building_coal_mine
				level >= 5
			}
		}
	}

	prosperity_modifier = {
		country_tech_spread_mult = 0.1
	}

	ai_will_do = {
		has_technology_researched = steam_donkey
		has_technology_researched = railways
		any_scope_state = {
			OR = {
				state_region = s:STATE_SHANXI
				state_region = s:STATE_ZHILI
			}
			is_incorporated = yes
		}
	}

	ai_construction_targets = {
		building_coal_mine = {
			level = 5
			state_trigger = {
				OR = {
					state_region = s:STATE_SHANXI
					state_region = s:STATE_ZHILI
				}
				is_incorporated = yes
			}
		}
	}

	ai_weight = {
		value = 3 # Higher base value for flavored companies
	}
}
```

### 工部营缮总局（统一建设联合体）

地点：北京
钢铁厂、工具厂、玻璃厂、铅矿（可选）
+20% 建造部门吞吐

```

```

### 户部农业银行

地点：北京
水稻、茶叶、烟草、牧场（可选）

```
#Da-Qing Bank / Bank of China
company_Da_Qing_Bank = {
	icon = "gfx/interface/icons/company_icons/historical_company_icons/da_qingbank.png" 
	background = "gfx/interface/icons/company_icons/company_backgrounds/comp_illu_manufacturing_light.dds"
	
	flavored_company = yes
	preferred_headquarters = { STATE_BEIJING }
	
	category = aristocrat_owned
	
	possible_prestige_goods = {
		#prestige_good_generic_currency_paper
	}
	
	building_types = {
		building_rice_farm
		building_tea_plantation
		building_tobacco_plantation
	}
	
	extension_building_types = {	
		building_livestock_ranch
	}
	
	potential = {
		has_game_rule = banks_enabled
		has_interest_marker_in_region = sr:region_north_china	
	}
	
	attainable = {
		hidden_trigger = { # Hide attainable if it's always fulfilled by possible
			any_scope_state = {
				state_region = s:STATE_BEIJING
			}
		}
	}	
	
	possible = {
		any_scope_state = {
			state_region = s:STATE_BEIJING
			is_incorporated = yes
			any_scope_building = {
				is_building_type = building_financial_district
				level >= 25
			}
		}
		has_technology_researched = international_exchange_standards
		unique_companies_has_bank = no
	}
	
	prosperity_modifier = {
		state_trade_advantage_mult = 0.1

		country_loan_interest_rate_mult = -0.025
        country_private_construction_allocation_mult = 0.1		
		
		state_farmers_investment_pool_contribution_add = 0.02 #<--
		state_shopkeepers_investment_pool_contribution_add = 0.02 #<--
		state_clergymen_investment_pool_contribution_add = 0.04
		state_aristocrats_investment_pool_contribution_add = 0.04
		state_capitalists_investment_pool_contribution_add = 0.065
		
		building_nationalization_investment_return_add = 0.075 #<--
		country_government_dividends_reinvestment_add = 0.075 #<--
		country_government_dividends_efficiency_add = 0.075 #<--
		
		country_max_companies_add = 1
	}
	
	ai_will_do = {
	    unique_companies_has_bank = no
	    has_technology_researched = international_exchange_standards
		any_scope_state = {
			state_region = s:STATE_BEIJING
			is_incorporated = yes
		}
	}

	ai_construction_targets = {
		building_paper_mill = {
			level = 5
			state_trigger = {
				state_region = s:STATE_BEIJING
			}
		}
	}
	ai_weight = {
		value = 5 # Higher base value for flavored companies
	}
}
```

### 江南制造总局

地点：苏州
武器厂、机器厂
+10 每周最大建造进度
名贵：名贵武器

```
# Jiangnan Arsenal
company_Jiangnan_Arsenal = {
	icon = "gfx/interface/icons/company_icons/basic_metalworks.dds"
	background = "gfx/interface/icons/company_icons/company_backgrounds/comp_illu_manufacturing_heavy.dds"
	
	flavored_company = yes
	preferred_headquarters = { STATE_SUZHOU }
	
	category = bureaucrat_owned
	
	possible_prestige_goods = {
		prestige_good_generic_small_arms
	}

	building_types = {  #11
		building_arms_industry
		building_tooling_workshop
		building_munition_plant
	}
	
	extension_building_types = {
		building_shipyard
	}

	potential = {
		has_interest_marker_in_region = sr:region_south_china	
	}
	
	attainable = {
		hidden_trigger = { # Hide attainable if it's always fulfilled by possible
			any_scope_state = {
				state_region = s:STATE_SUZHOU
			}
		}
	}	
	
	possible = { 
		any_scope_state = {
			state_region = s:STATE_SUZHOU
			is_incorporated = yes
			any_scope_building = {
				is_building_type = building_tooling_workshop
				level >= 3
			}
		}
	}
	
	prosperity_modifier = {
		unit_army_defense_mult = 0.05 #10
		country_max_weekly_construction_progress_add = 10
	}	
	

	ai_will_do = {
		any_scope_state = {
			state_region = s:STATE_SUZHOU
			is_incorporated = yes
		}
	}

	ai_construction_targets = {
		building_tooling_workshop = {
			level = 5
			state_trigger = {
				state_region = s:STATE_SUZHOU
			}
		}
	}
	ai_weight = {
		value = 3 # Higher base value for flavored companies
	}
}

```

### 轮船招商总局（苏伊士运河公司）

地点：苏伊士
造船厂、港口

### 南洋拓殖公司

地点：广东
橡胶种植园、伐木、咖啡、石油（可选）
+20% 橡胶、石油吞吐
+10% 殖民成长速度

```
company_NanyangCompany = {
	icon = "gfx/interface/icons/company_icons/basic_forestry.dds"
	background = "gfx/interface/icons/company_icons/company_backgrounds/comp_illu_manufacturing_light.dds"
	
	flavored_company = yes
	preferred_headquarters = { STATE_GUANGDONG }
	
	possible_prestige_goods = {
		prestige_good_redwood
	}

	
	building_types = {  #17
		building_logging_camp
		building_rubber_plantation
		building_coffee_plantation
	}
	
	extension_building_types = {
		building_port
		building_oil_rig
	}
	
	potential = {
		has_interest_marker_in_region = sr:region_south_china
	}
	
	attainable = {
		hidden_trigger = { # Hide attainable if it's always fulfilled by possible
			any_scope_state = {
				state_region = s:STATE_GUANGDONG
			}
		}
	}		
	
	possible = {
		any_scope_state = {
			state_region = s:STATE_GUANGDONG
			is_incorporated = yes
			any_scope_building = {
				is_building_type = building_logging_camp
				level >= 3
			}
		}
	}
	
	prosperity_modifier = {
		building_group_bg_logging_throughput_add = 0.13 #17
	}


	
	ai_will_do = {
		any_scope_state = {
			state_region = s:STATE_GUANGDONG
			is_incorporated = yes
		}
	}

	ai_construction_targets = {
		building_logging_camp = {
			level = 5
			state_trigger = {
				state_region = s:STATE_GUANGDONG
			}
		}
	}
	ai_weight = {
		value = 3 # Higher base value for flavored companies
	}	
}

```

