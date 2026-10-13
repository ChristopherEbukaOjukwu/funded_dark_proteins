1. The first thing was to download the NIH IDG R03 from https://druggablegenome.net/R03-Awards; downloaded on 10/12/2026.
   it includes 98 rows with IDG Protein Family and Specific Protein names---e.g. Kinase - RIOK3
2. We match the gene names to HGNC  and record the year each gene appeared on eligibility list using scripts/01_prepare_idg_genes.py --eligibility    and saved in data/processed/r03_gene_award_links.tsv and data/processed/idg_eligibility_by_gene.tsv. including non-funded genes as control
3. And then we got the project funding start dates from NIH RePorter using python3 python3 scripts/01_prepare_idg_genes.py --controls and saved in: data/processed/r03_award_dates.tsv and data/processed/r03_gene_funding_dates.tsv.
4. Publications were gotten from PubMed using python3 scripts/03_collect_gene_publications.py (python3 scripts/03_collect_gene_publications.py --max-human-genes-per-paper 10) and saved in data/processed/idg_gene_pubmed_links_2010_2025.tsv and data/processed/idg_gene_publications_annual_2010_2025.tsv
5. Matching funded to comparable unfunded genes using scripts/04_match_idg_controls.py and saved at data/processed/idg_match_review.tsv and  data/processed/idg_match_candidate_ranks.tsv
6. Bio information was gotten using  python3 scripts/05_collect_experimental_go.py and saved in data/processed/idg_go_experimental_pmid_evidence.tsv and data/processed/idg_go_experimental_annual_2010_2025.tsv
7. Chembl scripts/05_collect_experimental_go.py and Saved: data/processed/idg_chembl_target_mapping.tsv; data/processed/idg_chembl_potent_activity_evidence.tsv; data/processed/idg_chembl_annual_2010_2025.tsv
8. Protein databank scripts/07_collect_pdb_structures.py and Saved: data/processed/idg_pdb_gene_mapping.tsv; data/processed/idg_pdb_experimental_entries.tsv; data/processed/idg_pdb_annual_2010_2025.tsv.
9. GWAS was gotten using scripts/09_collect_gwas_catalog.py and Saved: data/processed/idg_gwas_catalog_intragenic_pmid_evidence.tsv; data/processed/idg_gwas_catalog_gene_coverage.tsv; data/processed/idg_gwas_catalog_intragenic_annual_2010_2025.tsv.
10. Data is integrated in scripts/10_build_idg_analysis_panel.py and Saved: data/processed/idg_integrated_gene_year_2010_2025.tsv; data/processed/idg_matched_pair_year_2010_2025.tsv.
11. Analyyzing attention using scripts/11_analyze_attention_go.py and Saved: data/processed/idg_attention_go_gene_changes.tsv
Saved: data/processed/idg_attention_go_summary.tsv
Saved: data/processed/idg_attention_go_event_profiles.tsv
Saved: data/processed/idg_attention_go_gene_event_years.tsv
Saved: data/processed/idg_attention_go_gene_distribution.tsv
Saved: data/processed/idg_attention_go_early_shifts.tsv
13. Getting funding links using scripts/13_audit_r03_publication_links.py and Saved: data/processed/idg_r03_reporter_grant_pmid_links.tsv
Saved: data/processed/idg_r03_gene_pmid_attribution.tsv
Saved: data/processed/idg_r03_publication_attribution_annual.tsv
Saved: data/processed/idg_r03_publication_attribution_event.tsv
Saved: data/processed/idg_r03_publication_attribution_summary.tsv
