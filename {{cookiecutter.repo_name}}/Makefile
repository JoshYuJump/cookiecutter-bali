env:
	pip3 install wheel pre-commit git+https://github.com/Ed-XCF/bali-cli.git@v0.5.7#egg=bali-cli
	pre-commit install
	rm -rf venv
	python3 -m venv --system-site-packages venv
	. venv/bin/activate \
	&& pip3 install -r requirements_dev.txt

docker:
	pip3 install wheel pre-commit git+https://github.com/Ed-XCF/bali-cli.git@v0.5.7#egg=bali-cli
	pre-commit install
	docker build --rm --build-arg DEPS=requirements_dev . -t {{cookiecutter.repo_name}}

migration:
	alembic revision --autogenerate

migrate:
	alembic upgrade head
