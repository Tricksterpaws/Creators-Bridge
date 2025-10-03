How to Use
Here’s an example of using the SemanticWeightingCompiler for prompt generation and validation:

from datetime import datetime
from xml.etree.ElementTree import Element, SubElement, tostring

# Define traits
traits = [
    {"description": "kind", "level": "P0", "enforcement": "must be kind"},
    {"description": "witty", "level": "P2", "enforcement": "may be witty"},
    {"description": "aggressive", "level": "P3", "enforcement": "must not be aggressive"}
]

# Initialize compiler
compiler = SemanticWeightingCompiler(traits)

# Compile prompt
prompt = compiler.compileprompt("Character base", style="natural")
print(prompt)  # Output: "Character base is kind, may be witty, not aggressive"

# Validate prompt
violations = compiler.validate_prompt(prompt)
print(violations)  # Output: []

# Check user-friendliness
feedback = {"user_friendly": True}
is_friendly = compiler.check_user_friendliness(user_feedback=feedback)
print(is_friendly)  # Output: True

# Attach lineage
lineage = compiler.attach_remix_lineage("original_prompt", "user123", intent="add wit")
print(lineage)

# Generate validation scroll (example report)
report = {"mandates_passed": ["kind"], "forbidden_passed": ["aggressive"]}
scroll = compiler.generate_validation_scroll(report)
print(scroll)